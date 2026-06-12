partizione ampia 64GB (2^36B)   blocchi da 1KB   bit di indirizzi multiplo di 8   file da 1,5MB

5.A) ext2fs
   i-node da 128B quello principale ha 8 indici e 1 per I,II,III indirezione
   1,5MB = 1536KB/1KB = 1536 blocchi
   64GB/1KB = 2^26 quindi 26bit indirizzabili che si arrotondano a 32bit = 4B
   prima indirezione è 128B/4B = 32 indici di blocchi
   1536 - (i-node principale) - (prima indirezione) = 1536 - 8 - 32 = 1496 blocchi rimanenti
   massimi blocchi con la seconda indirezione = 32^2 = 1024
   1496-1024= 472 serve quindi anche la terza indirezione con 15 i-node poichè 15x32=480 che bastano per completare i blocchi rimanenti
   (1) + (1) + (1 + 32) + (1 + 1 + 15) = 52 i-node servono
   52x128B = 6,5 KB dimensione su disco degli i-node
   6,5KB + 1536 KB = 1542,5 KB peso su disco occupato per un file da 1,5MB in ext2fs
   rapporto inflattivo = 6,5KB/1536KB= 0.004%

5.B) FAT
   rapporto inflattivo = dimensione FAT/file rappresentato x 4B (perchè si usa FAT32, dato che FAT16 non basta per 26bit indirizzabili)
   2^26 x 4B = 256MB dimensione FAT
   (2^26 sono il numero di celle trovate in precedenza)
   256MB/1.5MB=170.66 -> 17066%

5.C) NTFS
   nel caso di un file scritto su blocchi contigui ma ordine inverso.
   record da 1KB con 408B per il campo dati nel record principale e 800B nel secondario
   il record principale contiene 408B - 8B(intestazione) = 400B / 8B = 50
   mentre il secondario 800B / 8B = 100
   quindi 1536-50 = 1486 blocchi rimanenti tolto il record principale
   e 1486/100 = 14,86 ~ 15 record secondari
   quindi sono 16 record in tutto
   16 * 1KB = 16KB
   rapporto inflattivo = 16KB/1.536KB = 0.0104 -> 1.04%

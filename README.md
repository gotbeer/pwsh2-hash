# pwsh2-hash
Copypaste implementation of Get-Filehash in Powershell 2.0 and example of usage. "Horrible piece of shit" version.

Get the folder or file and save MD5hash to file.
```
.\hashToFile.ps1 -folderPath scriptkiddie.exe -resultFile MD5.txt
```


### single file
```
PS C:\Users\builder> .\hashToFile.ps1 kek.txt MD5.txt

PS C:\Users\builder> cat .\MD5.txt
0ee556e32fd00fe55200c00b2e83ad2b  	 \kek.txt
```

Wildcard supported in the filename. It works recursive to the current folder.
```
PS C:\Users\builder> .\hashToFile.ps1 kek* MD5.txt

PS C:\Users\builder> cat .\MD5.txt
3326a522fcbe7041b1c27388676c01cd  	 \tsev\kek
0ee556e32fd00fe55200c00b2e83ad2b  	 \kek.txt
```

### folder
It works recursive to the selected folder
```
PS C:\Users\builder> .\hashToFile.ps1 .\testFolder resultFileMD5.txt

PS C:\Users\builder> cat .\resultFileMD5.txt
e3d262c7a56dbac6d95b51377842361b        \testFolder\123
2f53aff628641ea77575eb7ac45b5882        \testFolder\456
```
```
PS C:\Users\builder> .\hashToFile.ps1 tset MD5.txt

PS C:\Users\builder> cat .\MD5.txt
2518faacc0d02b98919a0263e684c810  	 \tset\12\342423432
fafa894136a7e4c55db2891ceeb6d011  	 \tset\31232131231
2518faacc0d02b98919a0263e684c810  	 \tset\12\123
2518faacc0d02b98919a0263e684c810  	 \tset\rre
2518faacc0d02b98919a0263e684c810  	 \tset\rrw
```

Wildcard not supported in the folders name.


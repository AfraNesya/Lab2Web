# Lab2Web
<p><b> Nama    :   Afra Nesya Apriyanthi </p>
<p><b> NIM     :   312110614 </p>
<p><b> Kelas   :   TI.21.C1 </p>
<p><b> Mata Kuliah : Pemrograman Web</p>
<p><b> Tugas Pertemuan 3 </p>

# Tugas
![gambar 1](gambar/soal.jpeg)

<p>file index.php</p>
```php
<!DOCTYPE html>
<html>
<head>
<title>Tugas PHP</title>
</head>
<body>
<form action="output.php" method="post">
<table>
    <tr>
        <td width="100"> Nama </td>
        <td> : <input type="text" name="nama" /></td> 
    </tr>     
    <tr>
        <td>Tanggal Lahir </td>
        <td> : <input type="date" name="tanggal_lahir"></td>
	</tr>
    <tr> 
        <td> Pekerjaan </td>
        <td> : <input type="radio" name="pekerjaan" value="Karyawan"/>Karyawan
        <input type="radio" name="pekerjaan" value="PNS"/>PNS
        <input type="radio" name="pekerjaan" value="Petani"/>Petani
        <input type="radio" name="pekerjaan" value="Wiraswasta"/>Wiraswasta</td>
    </tr>	
    <tr>
        <td></td>
        <td> <input type="submit" value="kirim"/> </td>
    </tr>
</table>
</form>
</body>
</html>
```

<p>lalu buat output.php</p>
```php
<title> Output </title>
<?php
    
    $tanggal_lahir = new DateTime($_POST['tanggal_lahir']);
    $sekarang = new DateTime("today");
    if ($tanggal_lahir > $sekarang) { 
    $thn = "0";
    $bln = "0";
    $tgl = "0";
    }
    $thn = $sekarang->diff($tanggal_lahir)->y;
    $bln = $sekarang->diff($tanggal_lahir)->m;
    $tgl = $sekarang->diff($tanggal_lahir)->d;

    echo 'Nama      	:  ' . $_POST['nama'];
    echo "<br>";
    echo "Tanggal Lahir : ". $_POST['tanggal_lahir'];
    echo "<br>";
    echo "Usia    		: ";
    echo $thn." tahun ". $bln. " bulan " . $tgl. " hari";
    echo "<br>";
    echo "Pekerjaan     : " . $_POST['pekerjaan'];
    echo "<br>";


    $pekerjaan = ($_POST['pekerjaan']);
    switch ($pekerjaan){
        case "Karyawan Swasta": echo "Gaji    	 : Rp 4.500.000";break;
        case "Pegawai Negeri Sipil": echo "Gaji  : Rp 3.000.000";break;
        case "Wiraswasta": echo "Gaji   		 : Rp 8.000.000";break;
    }
?>
```

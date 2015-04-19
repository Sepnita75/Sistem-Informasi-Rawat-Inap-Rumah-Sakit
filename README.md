# Sistem-Informasi-Rawat-Inap_Rumah-Sakit
Tugas OOP Praktikum

/*
 * To change this template, choose Tools | Templates
 * and open the template in the editor.
 */
package rumahsakit;

import java.util.Date;
import java.util.Calendar;
import java.text.SimpleDateFormat;

/**
 *
 * @author TOSHIBA
 */
public class RumahSakit {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) throws Exception {
        // TODO code application logic here
        
        Dokter dokter1 = new Dokter();
        dokter1.setNama("Dr. Rosalinda");
        try {
            dokter1.setNidok("5413895761029389");
        } catch (Exception e) {
            System.out.println("Terjadi error : " + e.getMessage());
        }
        dokter1.setSpesialis("Bedah jantung");
        try {
            dokter1.setNoTlpn("087541278831");
        } catch (Exception e) {
            System.out.println("Terjadi error : " + e.getMessage());
        }
        
        Alamat alamatdokter = new Alamat();
        alamatdokter.setJalan("Jl. Diponegoro");
        alamatdokter.setKota("Jakarta");
        alamatdokter.setProvinsi("DKI Jakarta");
        dokter1.setAlamat(alamatdokter);
        cetakDokter(dokter1);
        cetakAlamat(alamatdokter);
        
        
        Perawat perawat1 = new Perawat();
        
        perawat1.setNama("Mawar");
        try {
            perawat1.setId("867367");
        } catch (Exception e) {
            System.out.println("Terjadi error : " + e.getMessage());
        }
        perawat1.setShift("2");
        
        
        Alamat alamatperawat = new Alamat();
        alamatperawat.setJalan("Jl. Kemana saja");
        alamatperawat.setKota("Jakarta");
        alamatperawat.setProvinsi("DKI Jakarta");
        perawat1.setAlamat(alamatperawat);
        cetakPerawat(perawat1);
        cetakAlamat(alamatperawat);
        
        
        Pasien pasien1 = new Pasien();
        pasien1.setNama("Bakrie");
        pasien1.setNoKode("34566783");
        try {
            pasien1.setJenisKelamin("Laki-laki");
        } catch (Exception e) {
            System.out.println("Terjadi error : " + e.getMessage());
        }
        pasien1.setUsia(35);
        pasien1.setPenyakit("Aterosklerosis");
        pasien1.setRiwayatPenyakit("Diabetes");
        
        Alamat alamatpasien = new Alamat();
        alamatpasien.setJalan("Jl. jalanan");
        alamatpasien.setKota("Jakarta");
        alamatpasien.setProvinsi("DKI Jakarta");
        pasien1.setAlamat(alamatpasien);
        
        
        Ttl ttlpasien = new Ttl();
        ttlpasien.setTempat("Sidney");
        
        Calendar cal2 = Calendar.getInstance();
        cal2.set(1980, 01, 04);
        Date ttl = cal2.getTime();
        ttlpasien.setTglLahir(ttl);
        pasien1.setTtl(ttlpasien);
        
        cetakPasien(pasien1);
        cetakAlamat(alamatpasien);
        cetakTtl(ttlpasien);
        
        Obat obat1 = new Obat();
        try {
            obat1.setNoBatch("675632");
        } catch (Exception e) {
            System.out.println("Terjadi error : " + e.getMessage());
        }
        try {
            obat1.setNoReg("DEF123456789012");
        } catch (Exception e) {
            System.out.println("Terjadi error : " + e.getMessage());
        }
        obat1.setNamaObat("Paracetamol");
        obat1.setBentukObat("Tablet");
        obat1.setEfekSamping("Mual");
        
        Date pembuatan;
        Calendar cal = Calendar.getInstance();
        cal.set(Calendar.YEAR, 2015);
        cal.set(Calendar.MONTH, Calendar.APRIL);
        cal.set(Calendar.DATE, 14);
        pembuatan = cal.getTime();
        obat1.setMgfDate(pembuatan);
        
        Date kadaluarsa;
        Calendar cal1 = Calendar.getInstance();
        cal1.set(Calendar.YEAR, 2016);
        cal1.set(Calendar.MONTH, Calendar.APRIL);
        cal1.set(Calendar.DATE, 14);
        kadaluarsa = cal1.getTime();
        obat1.setExpDate(kadaluarsa);
        
        obat1.setHET(100000);
        obat1.setIndikasi("Analgesik");
        obat1.setJenisObat("Obat bebas");
        obat1.setJmlObat(500);
        obat1.setProdusen("PT. Pratapa Nirmala");
        cetakObat(obat1);
        
        Ruangan ruangan1 = new Ruangan();
        ruangan1.setBagian("Melati");
        ruangan1.setKelas("VIP");
        ruangan1.setKategori("Dewasa");
        ruangan1.setTarif(1978000);
        ruangan1.setKategorikeperawatan("Internis dan Bedah");
        ruangan1.setFasilitas("TV, AC, Toilet dalam, kulkas");
        cetakRuangan(ruangan1);
        
        RawatInap rawatinap1 = new RawatInap();
        rawatinap1.setDokter(dokter1);
        rawatinap1.setPetugas(perawat1);
        rawatinap1.setPasien(pasien1);
        rawatinap1.setObat(obat1);
        rawatinap1.setKamar(ruangan1);
        rawatinap1.setTglMasuk(new Date());
        rawatinap1.setTglKeluar(new Date());
        
        
    }
    
    static void cetakDokter(Dokter dokter) {
        System.out.println("\n\tInformasi dokter yang menangani pasien\n");
        System.out.println("Nama dokter\t: " + dokter.getNama());
        System.out.println("Nidok\t\t: " + dokter.getNidok());
        System.out.println("Spesialis\t: " + dokter.getSpesialis());
        System.out.println("No. Telpon\t: " + dokter.getNoTlpn());
    }
    
    static void cetakPerawat(Perawat perawat) {
        System.out.println("\n\tInformasi perawat yang merawat pasien\n");
        System.out.println("Nama perawat\t: " + perawat.getNama());
        System.out.println("No. ID\t\t: " + perawat.getId());
        System.out.println("Shift\t\t: " + perawat.getShift());
    }
    
    static void cetakPasien(Pasien pasien) {
        System.out.println("\n\tInformasi pasien\n");
        System.out.println("Nama pasien\t: " + pasien.getNama());
        System.out.println("No. Kode\t: " + pasien.getNoKode());
        System.out.println("Jenis Kelamin\t: " + pasien.getJenisKelamin());
        System.out.println("Usia pasien\t: " + pasien.getUsia());
        System.out.println("Penyakit\t: " + pasien.getPenyakit());
        System.out.println("Riwayat Kesehatan\t: " + pasien.getRiwayatPenyakit());
    }
    
    static void cetakObat(Obat obat) {
        System.out.println("\n\tInformasi obat\n");
        System.out.println("Nama obat\t\t: " + obat.getNamaObat());
        System.out.println("No. Batch\t\t: " + obat.getNoBatch());
        System.out.println("No. Reg BPOM\t\t: " + obat.getNoReg());
        System.out.println("Jenis obat\t\t: " + obat.getJenisObat());
        System.out.println("Bentuk obat\t\t: " + obat.getBentukObat());
        System.out.println("Efek samping\t\t: " + obat.getEfekSamping());
        System.out.println("Indikasi\t\t: " + obat.getIndikasi());
        System.out.println("Harga Eceran Tertinggi\t: " + obat.getHET());
        System.out.println("Produsen\t\t: " + obat.getProdusen());
        System.out.println("Tanggal Pembuatan\t: " + obat.getMgfDate());
        System.out.println("Tanggal kadaluarsa\t: " + obat.getExpDate());
        System.out.println("Jumlah obat yang tersedia\t: " + obat.getJmlObat());
    }
    
    static void cetakRuangan(Ruangan ruangan) {
        System.out.println("\n\tInformasi ruangan yang digunakan pasien\n");
        System.out.println("Bagian\t\t\t: " + ruangan.getBagian());
        System.out.println("Kelas\t\t\t: " + ruangan.getKelas());
        System.out.println("Kategori\t\t: " + ruangan.getKategori());
        System.out.println("Kategori ruangan\t: " + ruangan.getKategorikeperawatan());
        System.out.println("Fasilitas\t\t: " + ruangan.getFasilitas());
    }
    
    static void cetakAlamat(Alamat alamat) {
        System.out.println("\tInformasi Alamat yang bersangkutan");
        System.out.println("Jalan\t\t: " + alamat.getJalan());
        System.out.println("Kota\t\t: " + alamat.getKota());
        System.out.println("Provinsi\t: " + alamat.getProvinsi());
        
    }
    
    static void cetakTtl(Ttl ttl) {
        System.out.println("Tempat lahir\t: " + ttl.getTempat());
        System.out.println("Tanggal lahir\t: " + ttl.getTglLahir());
    }
}

public class Dokter {

    private String nama;
    private String nidok;
    private String spesialis;
    private Alamat alamat;
    private String noTlpn;

    /**
     * @return the nama
     */
    public String getNama() {
        return nama;
    }

    /**
     * @param nama the nama to set
     */
    public void setNama(String nama) throws Exception {
        this.nama = nama;
    }

    /**
     * @return the nidok
     */
    public String getNidok() {
        return nidok;
    }

    /**
     * @param nidok the nidok to set
     */
    public void setNidok(String nidok) throws Exception {
        for (int i = 0; i < 16; i++) {
            if (Character.isDigit(nidok.charAt(i))) {
                this.nidok = nidok;
            } else {
                throw new Exception("Nomor Induk Dokter harus berupa angka");
            }

        }

    }

    /**
     * @return the spesialis
     */
    public String getSpesialis() {
        return spesialis;
    }

    /**
     * @param spesialis the spesialis to set
     */
    public void setSpesialis(String spesialis) {
        this.spesialis = spesialis;
    }

    /**
     * @return the alamat
     */
    public Alamat getAlamat() {
        return alamat;
    }

    /**
     * @param alamat the alamat to set
     */
    public void setAlamat(Alamat alamat) {
        this.alamat = alamat;
    }

    /**
     * @return the noTlpn
     */
    public String getNoTlpn() {
        return noTlpn;
    }

    /**
     * @param noTlpn the noTlpn to set
     */
    public void setNoTlpn(String noTlpn) throws Exception {
        for (int i = 0; i < 12; i++) {
            if (Character.isDigit(noTlpn.charAt(i))) {
                this.noTlpn = noTlpn;
            } else {
                throw new Exception("Nomor Telepon harus berupa angka");
            }

        }

    }
}


import java.util.Date;
public class Obat {

    private String noBatch;
    private String noReg;
    private Date mgfDate;
    private Date expDate;
    private String namaObat;
    private String jenisObat;
    private String bentukObat;
    private String produsen;
    private int het;
    private String indikasi;
    private String efekSamping;
    private int jmlObat;

    /**
     * @return the noBatch
     */
    public String getNoBatch() {
        return noBatch;
    }

    /**
     * @param noBatch the noBatch to set
     */
    public void setNoBatch(String noBatch) {
        try {
            Integer.parseInt(noBatch);
        } catch (Exception e) {
            System.out.println("No Batch harus berupa angka");
        }
        this.noBatch = noBatch;
    }

    /**
     * @return the noReg
     */
    public String getNoReg() {
        return noReg;
    }

    /**
     * @param noReg the noReg to set
     */
    public void setNoReg(String noReg) {
        for (int i = 0; i < 3; i++) {
            if (Character.isDigit(noReg.charAt(i))) {
                return;
            }

            for (int j = 3; j < 15; j++) {
                if (!Character.isDigit(noReg.charAt(j))) {
                    return;
                }
            }
        }
        this.noReg = noReg;
    }

    /**
     * @return the mgfDate
     */
    public Date getMgfDate() {
        return mgfDate;
    }

    /**
     * @param mgfDate the mgfDate to set
     */
    public void setMgfDate(Date mgfDate) {
        this.mgfDate = mgfDate;
    }

    /**
     * @return the ExpDate
     */
    public Date getExpDate() {
        return expDate;
    }

    /**
     * @param ExpDate the ExpDate to set
     */
    public void setExpDate(Date expDate) {
        this.expDate = expDate;
    }

    /**
     * @return the namaObat
     */
    public String getNamaObat() {
        return namaObat;
    }

    /**
     * @param namaObat the namaObat to set
     */
    public void setNamaObat(String namaObat) {
        this.namaObat = namaObat;
    }

    /**
     * @return the jenisObat
     */
    public String getJenisObat() {
        return jenisObat;
    }

    /**
     * @param jenisObat the jenisObat to set
     */
    public void setJenisObat(String jenisObat) {
        this.jenisObat = jenisObat;
    }

    /**
     * @return the bentukObat
     */
    public String getBentukObat() {
        return bentukObat;
    }

    /**
     * @param bentukObat the bentukObat to set
     */
    public void setBentukObat(String bentukObat) {
        this.bentukObat = bentukObat;
    }

    /**
     * @return the produsen
     */
    public String getProdusen() {
        return produsen;
    }

    /**
     * @param produsen the produsen to set
     */
    public void setProdusen(String produsen) {
        this.produsen = produsen;
    }

    /**
     * @return the HET
     */
    public int getHET() {
        return het;
    }

    /**
     * @param HET the HET to set
     */
    public void setHET(int het) {
        this.het = het;
    }

    /**
     * @return the indikasi
     */
    public String getIndikasi() {
        return indikasi;
    }

    /**
     * @param indikasi the indikasi to set
     */
    public void setIndikasi(String indikasi) {
        this.indikasi = indikasi;
    }

    /**
     * @return the efekSamping
     */
    public String getEfekSamping() {
        return efekSamping;
    }

    /**
     * @param efekSamping the efekSamping to set
     */
    public void setEfekSamping(String efekSamping) {
        this.efekSamping = efekSamping;
    }

    /**
     * @return the jmlObat
     */
    public int getJmlObat() {
        return jmlObat;
    }

    /**
     * @param jmlObat the jmlObat to set
     */
    public void setJmlObat(int jmlObat) {

        this.jmlObat = jmlObat;
    }
}


public class Pasien {

    private String nama;
    private String noKode;
    private String jenisKelamin;
    private Ttl ttl;
    private int usia;
    private Alamat alamat;
    private String penyakit;
    private String riwayatPenyakit;

    /**
     * @return the nama
     */
    public String getNama() {
        return nama;
    }

    /**
     * @param nama the nama to set
     */
    public void setNama(String nama) throws Exception {
        this.nama = nama;

    }

    /**
     * @return the noKode
     */
    public String getNoKode() {
        return noKode;
    }

    /**
     * @param noKode the noKode to set
     */
    public void setNoKode(String noKode) {
        Integer.parseInt(noKode);

        this.noKode = noKode;
    }

    /**
     * @return the jenisKelamin
     */
    public String getJenisKelamin() {
        return jenisKelamin;
    }

    /**
     * @param jenisKelamin the jenisKelamin to set
     */
    public void setJenisKelamin(String jenisKelamin) throws Exception {
        switch (jenisKelamin) {
            case "Laki-laki":
                this.jenisKelamin = jenisKelamin;
                break;
            case "Perempuan":
                this.jenisKelamin = jenisKelamin;
                break;
            default:
                throw new Exception("Jenis Kelamin salah");

        }
    }

    /**
     * @return the ttl
     */
    public Ttl getTtl() {
        return ttl;
    }

    /**
     * @param ttl the ttl to set
     */
    public void setTtl(Ttl ttl) {
        this.ttl = ttl;
    }

    public int getUsia() {
        return usia;
    }

    /**
     * @param usia the usia to set
     */
    public void setUsia(int usia) {
        this.usia = usia;
    }

    /**
     * @return the alamat
     */
    public Alamat getAlamat() {
        return alamat;
    }

    /**
     * @param alamat the alamat to set
     */
    public void setAlamat(Alamat alamat) {
        this.alamat = alamat;
    }

    /**
     * @return the penyakit
     */
    public String getPenyakit() {
        return penyakit;
    }

    /**
     * @param penyakit the penyakit to set
     */
    public void setPenyakit(String penyakit) {
        this.penyakit = penyakit;
    }

    /**
     * @return the riwayatPenyakit
     */
    public String getRiwayatPenyakit() {
        return riwayatPenyakit;
    }

    /**
     * @param riwayatPenyakit the riwayatPenyakit to set
     */
    public void setRiwayatPenyakit(String riwayatPenyakit) {
        this.riwayatPenyakit = riwayatPenyakit;
    }
    /**
     * @return the usia
     */
}


public class Perawat {

    private String nama;
    private String id;
    private String shift;
    private Alamat alamat;

    /**
     * @return the nama
     */
    public String getNama() {
        return nama;
    }

    /**
     * @param nama the nama to set
     */
    public void setNama(String nama) throws Exception {
        this.nama = nama;
    }

    /**
     * @return the id
     */
    public String getId() {
        return id;
    }

    /**
     * @param id the id to set
     */
    public void setId(String id) throws Exception {
        Integer.parseInt(id);
        this.id = id;
    }

    /**
     * @return the shift
     */
    public String getShift() {
        return shift;
    }

    /**
     * @param shift the shift to set
     */
    public void setShift(String shift) throws Exception {
        Integer.parseInt(shift);
        this.shift = shift;
    }

    /**
     * @return the alamat
     */
    public Alamat getAlamat() {
        return alamat;
    }

    /**
     * @param alamat the alamat to set
     */
    public void setAlamat(Alamat alamat) {
        this.alamat = alamat;
    }
}

import java.util.Date;

/**
 *
 * @author TOSHIBA
 */
public class RawatInap {

    private Dokter dokter;
    private Perawat petugas;
    private Pasien pasien;
    private Obat obat;
    private Ruangan kamar;
    private Date tglMasuk;
    private Date tglKeluar;

    /**
     * @return the dokter
     */
    public Dokter getDokter() {
        return dokter;
    }

    /**
     * @param dokter the dokter to set
     */
    public void setDokter(Dokter dokter) {
        this.dokter = dokter;
    }

    /**
     * @return the petugas
     */
    public Perawat getPetugas() {
        return petugas;
    }

    /**
     * @param petugas the petugas to set
     */
    public void setPetugas(Perawat petugas) {
        this.petugas = petugas;
    }

    /**
     * @return the pasien
     */
    public Pasien getPasien() {
        return pasien;
    }

    /**
     * @param pasien the pasien to set
     */
    public void setPasien(Pasien pasien) {
        this.pasien = pasien;
    }

    /**
     * @return the obat
     */
    public Obat getObat() {
        return obat;
    }

    /**
     * @param obat the obat to set
     */
    public void setObat(Obat obat) {
        this.obat = obat;
    }

    /**
     * @return the kamar
     */
    public Ruangan getKamar() {
        return kamar;
    }

    /**
     * @param kamar the kamar to set
     */
    public void setKamar(Ruangan kamar) {
        this.kamar = kamar;
    }

    /**
     * @return the tglMasuk
     */
    public Date getTglMasuk() {
        return tglMasuk;
    }

    /**
     * @param tglMasuk the tglMasuk to set
     */
    public void setTglMasuk(Date tglMasuk) {
        this.tglMasuk = tglMasuk;
    }

    /**
     * @return the tglKeluar
     */
    public Date getTglKeluar() {
        return tglKeluar;
    }

    /**
     * @param tglKeluar the tglKeluar to set
     */
    public void setTglKeluar(Date tglKeluar) {
        this.tglKeluar = tglKeluar;
    }
}

public class Ruangan {

    private String bagian;
    private String kelas;
    private int tarif;
    private String kategori;
    private String kategorikeperawatan;
    private String fasilitas;

    /**
     * @return the bagian
     */
    public String getBagian() {
        return bagian;
    }

    /**
     * @param bagian the bagian to set
     */
    public void setBagian(String bagian) {
        this.bagian = bagian;
    }

    /**
     * @return the kelas
     */
    public String getKelas() {
        return kelas;
    }

    /**
     * @param kelas the kelas to set
     */
    public void setKelas(String kelas) {
        this.kelas = kelas;
    }

    /**
     * @return the tarif
     */
    public int getTarif() {
        return tarif;
    }

    /**
     * @param tarif the tarif to set
     */
    public void setTarif(int tarif) {
        this.tarif = tarif;
    }

    /**
     * @return the kategori
     */
    public String getKategori() {
        return kategori;
    }

    /**
     * @param kategori the kategori to set
     */
    public void setKategori(String kategori) {
        this.kategori = kategori;
    }

    /**
     * @return the kategorikeperawatan
     */
    public String getKategorikeperawatan() {
        return kategorikeperawatan;
    }

    /**
     * @param kategorikeperawatan the kategorikeperawatan to set
     */
    public void setKategorikeperawatan(String kategorikeperawatan) {
        this.kategorikeperawatan = kategorikeperawatan;
    }

    /**
     * @return the fasilitas
     */
    public String getFasilitas() {
        return fasilitas;
    }

    /**
     * @param fasilitas the fasilitas to set
     */
    public void setFasilitas(String fasilitas) {
        this.fasilitas = fasilitas;
    }
}


import java.util.Date;

/**
 *
 * @author TOSHIBA
 */
public class Ttl {

    private String tempat;
    private Date tglLahir;

    /**
     * @return the tempat
     */
    public String getTempat() {
        return tempat;
    }

    /**
     * @param tempat the tempat to set
     */
    public void setTempat(String tempat) {

        this.tempat = tempat;

    }

    /**
     * @return the tglLahir
     */
    public Date getTglLahir() {
        return tglLahir;
    }

    /**
     * @param tglLahir the tglLahir to set
     */
    public void setTglLahir(Date tglLahir) {
        this.tglLahir = tglLahir;
    }
}

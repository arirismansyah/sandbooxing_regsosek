<div align = "center">

# **SANDBOXING SCRIPT QUERY TOOLS REGSOSEK 2022 BPS PROVINSI SUMATERA SELATAN**

---
<div align = "center">

<img src = "assets/profile.png" width="100" height="100"></img>
### **Ari Rismansyah | @arirismansyah**



© Copyright 2022 - Ari Rismansyah – ari.rismansyah@bps.go.id

---

</div>

</div>


<br>

## **Deskripsi**

<div align = "justify">

Berikut ini merupakan scipt sandbox untuk explorasi dan identifikasi data hasil entri REGSOSEK 2022 BPS Provinsi Sumatera Selatan


</div>

<br>

### 01 - REKAP ERROR, WARNING, & BLANK PER PETUGAS ENTRI PER WILAYAH
```
SELECT kode_kec, kode_desa, kode_sls,  sls_nama, m_operator.realname, 
SUM (CASE WHEN status_dok = 'E' THEN 1 ELSE 0 END) AS jumlah_error,
SUM (CASE WHEN status_dok = 'W' THEN 1 ELSE 0 END) AS jumlah_warning,
SUM (CASE WHEN status_dok = '' THEN 1 ELSE 0 END) AS jumlah_blank
FROM t_rt, m_operator WHERE m_operator.id_operator = t_rt.kode_operator 
Group by kode_kec, kode_desa, kode_sls, sls_nama, m_operator.realname
order by realname

```




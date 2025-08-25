# Kubernetes Ödevi

Bu repository, çok düğümlü bir Kubernetes cluster kurulumu ve bazı ek servislerin entegrasyonunu içermektedir. Ödev kapsamında yapılanlar ve yapılamayan kısımlar aşağıda açıklanmıştır.

---

## 📌 Yapılanlar

### 1. Rook-Ceph Kurulumu
- Rook-Ceph CRD ve operator dosyaları uygulandı.
- Test amaçlı PVC ve pod’lar oluşturuldu ve çalışmaları test edildi.
- Pod’lar üzerinde interaktif testler (`kubectl exec`) gerçekleştirildi.
- StorageClass ve PVC durumları sürekli kontrol edildi.

### 2. ELK Stack Kurulumu
- Helm kullanılarak Elasticsearch ve Kibana kuruldu.
- Filebeat konfigürasyonu yapıldı ve ELK stack ile bağlantısı sağlandı.
- Kibana port forwarding ile erişilebilir hâle getirildi.

### 3. Cluster Konfigürasyonu
- Host network ve Flannel konfigürasyon dosyaları yönetildi.
- **RBAC (Role-Based Access Control) yapılandırıldı.**
- Aynı makinede başka bir kullanıcı oluşturulup (Master2) kubeconfig dosyası sertifikalanıp verildi.
- Git ile tüm dosyalar version kontrolüne alındı.


---

## ⚠️ Yapılamayanlar
- **Keycloak:** Ek bir sanal makine gerektirdiği için kurulamadı.
- **High Availability (HA):** `kubeadm init` sırasında gerekli flag eklenmediği için yapılamadı.
- **Load Balancer:** HA kurulmadığı için gerekli yapılandırma yapılmadı.

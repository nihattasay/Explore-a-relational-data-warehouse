# 📊 Azure Synapse Analytics: Relational Data Warehouse Exploration

Bu proje, Azure Synapse Analytics üzerinde relational veri ambarı mimarisinin nasıl çalıştığını incelemek ve temel veri analitiği sorgularını çalıştırmak amacıyla hazırlanmış bir laboratuvar uygulamasıdır.

---

## 📌 İçerik

Bu laboratuvarda:

- Azure Synapse Analytics workspace kurulumu  
- Dedicated SQL Pool başlatma  
- Veri ambarı şeması inceleme  
- Fact ve Dimension tablolarını sorgulama  
- Ranking ve Windowing fonksiyonlarının kullanımı  
- Approximate Count sorguları ile performans artırma

---

## 🚀 Kurulum

### Ön Gereksinimler:

- Azure aboneliği  
- Azure portal erişimi: [https://portal.azure.com](https://portal.azure.com)

### Adımlar:

1. Azure portalda Cloud Shell’i PowerShell ortamında başlatın.
2. Aşağıdaki komutla laboratuvar dosyalarını klonlayın:
   ```powershell
   rm -r dp203 -f
   git clone https://github.com/MicrosoftLearning/Dp-203-azure-data-engineer dp203

   Laboratuvar dizinine geçin ve kurulumu başlatın:

cd dp203/Allfiles/labs/08
./setup.ps1

Kurulum sırasında SQL Pool şifresini belirleyin ve not alın.

Kurulumun tamamlanmasını bekleyin (~15 dakika).

Kullanım

Synapse Studio üzerinden SQL script'leri ile:

    Yıllık satışları listeleyin

    Yıllık-aylık satış dağılımı yapın

    Bölgesel satış analizleri

    Ürün kategorisi bazlı satışlar

    Ranking ve windowing fonksiyonları ile detaylı sıralamalar

    Approximate Count fonksiyonuyla performanslı veri sayımları

Örnek Sorgu:

SELECT  d.CalendarYear AS Year,
        SUM(i.SalesAmount) AS InternetSalesAmount
FROM FactInternetSales AS i
JOIN DimDate AS d ON i.OrderDateKey = d.DateKey
GROUP BY d.CalendarYear
ORDER BY Year;

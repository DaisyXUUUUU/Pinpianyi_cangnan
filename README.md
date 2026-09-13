# Pinpianyi · Cangnan Recycling Operations

**Connecting resident pickup requests, field collection, and county-level recycling operations through a shared product workflow.**

Pinpianyi (拼便宜) is a recycling service design for Cangnan, Zhejiang, China. This repository presents the resident and collector mini-program interfaces alongside an operations dashboard for the county’s recycling network.

The case study focuses on translating a physical service into digital workflows: what residents submit, what collectors verify on site, how materials are handed over, and what operators need to see across facilities and vehicles.

> **Repository scope:** 60 interface images and a packaged Axure `.rp` prototype. These artifacts document product behavior and interaction design; this repository does not contain application source code or a runnable deployment. Values displayed in the screens are not presented here as verified business results.

![Cangnan recycling operations dashboard: orders, material volumes, facilities, vehicles, and alerts](%E6%95%B0%E6%8D%AE%E9%A9%BE%E9%A9%B6%E8%88%B1/%E6%80%BB%E8%A7%88/%E5%85%A8%E5%8E%BF%E8%8C%83%E5%9B%B4/%E6%80%BB%E8%A7%880.png)

## The operational problem

Recycling spans several handoffs. A resident estimates the material and requests collection; a collector verifies the actual category and weight, confirms compensation, and returns materials to a service point. Operators then need visibility into collection, sorting, storage, and transport.

The design brings these steps into related interfaces while accounting for differences between a resident’s initial request and the work performed in the field.

## Product surfaces

| Surface | Intended users | Workflows shown in the artifacts |
| --- | --- | --- |
| Resident mini-program | Residents | Select materials, request pickup, review reference prices, track orders, and view rewards and points. |
| Collector mini-program | Collection staff | Accept orders, review pickup details, confirm pricing and payment, create orders for residents, and submit station handovers. |
| Operations dashboard | Recycling network operators | Review county and township activity, service points, sorting centers, smart bins, vehicles, and operational alerts. |

## Walk through the service

1. **Request collection.** The resident selects a material category, address, pickup time, and estimated weight. Reference prices set expectations; the interface states that final category and weight depend on on-site verification.
2. **Complete the pickup.** The collector reviews the order, works through pricing, and confirms compensation through the payment options shown: environmental credits, WeChat transfer, or points.
3. **Hand materials over.** The collector proceeds to station submission, with separate designs for scan-and-weigh, manual entry, and submission without weighing.
4. **Review operations.** The dashboard presents orders, recycling volumes, material composition, payments, facility activity, vehicle statistics, and alerts at different geographic and operational levels.

These steps describe the product flow represented by the screens, rather than a verified backend integration.

## Design decisions relevant to Forward Deployed Engineering

### Capture what happens in the field

An estimated pickup weight is different from a verified collection weight. The resident flow makes that distinction explicit, and the collector flow includes on-site pricing and payment confirmation. This is a concrete example of turning an operational rule into a user-facing workflow.

### Support more than the standard path

The collector interface includes **ordering on behalf of a resident**, **manual handover entry**, and **submission without weighing**. These paths make the design useful for discussing how a service accommodates different collection and handover situations. The manual-entry screen captures material category, weight, notes, and a photo.

### Connect frontline activity to operational decisions

The dashboard shifts from individual orders to network oversight: county and township views, facility-level inventory movement, fleet activity, and severity-labeled alerts. The product connects the information needed to complete a pickup with the information needed to supervise the wider service.

### Represent different facility configurations

The sorting-center artifacts include both simplified and digitalized variants. They provide a basis for discussing how an interface should adapt to facilities with different operational setups; the repository does not establish which configurations were deployed.

Together, these artifacts support an FDE portfolio discussion about workflow discovery, domain modeling, operational exceptions, and solution communication. Engineering implementation, integration ownership, and deployment outcomes would need separate evidence.

## Selected screens

Start with these artifacts for a quick review. The original interface language is Chinese; the labels below explain the purpose of each screen in English.

| Artifact | What to look for |
| --- | --- |
| [Resident pickup request](%E5%B0%8F%E7%A8%8B%E5%BA%8F%E7%95%8C%E9%9D%A22.0/%E5%B1%85%E6%B0%91%E7%AB%AF/1.1%20%E5%9B%9E%E6%94%B6%E5%86%85%E9%A1%B5-%E5%88%9D%E5%AE%9A%E7%BB%86%E8%8A%82%EF%BC%8C%E6%94%B6%E4%BB%B6%E4%BA%BA%E4%B8%8A%E9%97%A8%E8%B0%83%E6%95%B4.vector_00.png) | Estimated weight, reference prices, and on-site verification. |
| [Collector payment confirmation](%E5%B0%8F%E7%A8%8B%E5%BA%8F%E7%95%8C%E9%9D%A22.0/%E5%9B%9E%E6%94%B6%E5%91%98%E7%AB%AF/1.2.4%E9%A6%96%E9%A1%B5-%E5%BE%85%E4%B8%8A%E9%97%A8-%E7%A1%AE%E8%AE%A4%E6%94%AF%E4%BB%98.vector_00.png) | Compensation options and an order-linked amount. |
| [Order on behalf of a resident](%E5%B0%8F%E7%A8%8B%E5%BA%8F%E7%95%8C%E9%9D%A22.0/%E5%9B%9E%E6%94%B6%E5%91%98%E7%AB%AF/2.0%E4%BB%A3%E5%AE%A2%E4%B8%8B%E5%8D%95%EF%BC%88%E4%BB%A5%E6%89%8B%E5%8A%A8%E8%BE%93%E5%85%A5%E4%B8%BA%E4%BE%8B%EF%BC%89.vector_00.png) | A collector-assisted entry point into the service. |
| [Manual station handover](%E5%B0%8F%E7%A8%8B%E5%BA%8F%E7%95%8C%E9%9D%A22.0/%E5%9B%9E%E6%94%B6%E5%91%98%E7%AB%AF/1.3.2%E9%A6%96%E9%A1%B5-%E5%BE%85%E4%BA%A4%E5%9B%9E%E7%AB%99%E7%82%B9-%E4%BA%BA%E5%B7%A5%E5%BD%95%E5%85%A5.vector_00.png) | Material category, weight, notes, and photo capture. |
| [Digitalized sorting center](%E6%95%B0%E6%8D%AE%E9%A9%BE%E9%A9%B6%E8%88%B1/%E5%88%86%E6%8B%A3%E4%B8%AD%E5%BF%83/%E6%95%B0%E5%AD%97%E5%8C%96/0.png) | Inbound, sorting, storage, outbound, and exception views. |
| [Simplified sorting center](%E6%95%B0%E6%8D%AE%E9%A9%BE%E9%A9%B6%E8%88%B1/%E5%88%86%E6%8B%A3%E4%B8%AD%E5%BF%83/%E7%AE%80%E6%98%93%E7%89%88/0.png) | An alternative facility view. |
| [Vehicle management](%E6%95%B0%E6%8D%AE%E9%A9%BE%E9%A9%B6%E8%88%B1/%E8%BD%A6%E8%BE%86%E7%AE%A1%E7%90%86/0.png) | The dedicated fleet operations screen. |

## Repository guide

```text
小程序界面2.0/                 Mini-program UI, version 2.0
├── 居民端/                   Resident screens
├── 回收员端/                 Collector screens
└── …                         Poster and business-card assets
数据驾驶舱/                   Operations dashboard
├── 总览/                     County and township overviews
├── 回收服务点/               Recycling service points
├── 分拣中心/                 Simplified and digitalized sorting centers
├── 智能回收箱/               Smart recycling bins
├── 车辆管理/                 Vehicle management
└── *.rp.zip                  Packaged Axure prototype
```

## Explore the artifacts

- **Browse on GitHub:** open the screen links above or explore the two asset directories. No installation is needed to view the PNGs.
- **Inspect the prototype:** download and extract the [Axure archive](%E6%95%B0%E6%8D%AE%E9%A9%BE%E9%A9%B6%E8%88%B1/%E5%8F%AF%E5%9B%9E%E6%94%B6%E6%95%B0%E6%8D%AE%E5%A4%A7%E5%B1%8F%E9%A9%BE%E9%A9%B6%E8%88%B1%EF%BC%888-7%EF%BC%89.rp.zip), then open the `.rp` file in a compatible version of Axure RP. The required Axure version is not recorded in the repository.
- **Clone the repository:**

```bash
git clone https://github.com/DaisyXUUUUU/Pinpianyi_cangnan.git
cd Pinpianyi_cangnan
```

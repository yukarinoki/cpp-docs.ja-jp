---
description: 詳細については、「CComObject、CComAggObject、および CComPolyObject の実装」を参照してください。
title: CComObject、CComAggObject、CComPolyObject の実装
ms.date: 11/04/2016
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
ms.openlocfilehash: e0cc8a6b65ec9d85249cd47e2f43cf1bec2b8ce2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147772"
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>CComObject、CComAggObject、CComPolyObject の実装

テンプレートクラス [CComObject](../atl/reference/ccomobject-class.md)、 [CComAggObject](../atl/reference/ccomaggobject-class.md)、および [CComPolyObject](../atl/reference/ccompolyobject-class.md) は、常に継承チェーン内の最も派生クラスです。 では `IUnknown` `QueryInterface` 、、、およびのすべてのメソッドを処理する必要があり `AddRef` `Release` ます。 さらに、 `CComAggObject` および `CComPolyObject` (集計されたオブジェクトに使用する場合) は、 `QueryInterface` 内部の unknown に必要な特殊な参照カウントおよびセマンティクスを提供します。

`CComObject`、 `CComAggObject` 、またはが使用されるかどうかは、 `CComPolyObject` 次のマクロのいずれかを宣言するかどうかによって異なります。

|マクロ|効果|
|-----------|------------|
|DECLARE_NOT_AGGREGATABLE|常に `CComObject` を使用します。|
|DECLARE_AGGREGATABLE|オブジェクトが集計されている場合はを、それ以外の場合はを使用 `CComAggObject` `CComObject` します。 `CComCoClass` このマクロが含まれているので、DECLARE_ * _AGGREGATABLE マクロがクラスで宣言されていない場合は、これが既定値になります。|
|DECLARE_ONLY_AGGREGATABLE|常に `CComAggObject` を使用します。 オブジェクトが集計されていない場合は、エラーを返します。|
|DECLARE_POLY_AGGREGATABLE|が呼び出されると、ATL によって **\<CYourClass> CComPolyObject** のインスタンスが作成され `IClassFactory::CreateInstance` ます。 作成時に、[外側の不明] の値がチェックされます。 NULL の場合は、 `IUnknown` 非集計オブジェクトに対してが実装されます。 外側の unknown が NULL でない場合、 `IUnknown` は集計オブジェクトに対して実装されます。|

とを使用する利点は、 `CComAggObject` `CComObject` の実装 `IUnknown` が、作成されるオブジェクトの種類に合わせて最適化されることです。 たとえば、非集計オブジェクトは参照カウントのみを必要としますが、集計されたオブジェクトには、内部不明の参照カウントと外部不明へのポインターの両方が必要です。

を使用する利点 `CComPolyObject` は、集計された `CComAggObject` `CComObject` ケースと非集計ケースを処理するためにとの両方のモジュールを使用しないことです。 1つの `CComPolyObject` オブジェクトが両方のケースを処理します。 つまり、モジュールには vtable のコピーと関数のコピーが1つだけ存在します。 Vtable が大きい場合は、モジュールのサイズを大幅に減らすことができます。 ただし、vtable が小さい場合、を使用する `CComPolyObject` と、とのように集計または非集計オブジェクトに対して最適化されていないため、モジュールサイズが少し大きくなり `CComAggObject` `CComObject` ます。

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)<br/>
[集計およびクラスファクトリマクロ](../atl/reference/aggregation-and-class-factory-macros.md)

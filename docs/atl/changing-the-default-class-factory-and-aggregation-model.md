---
description: '詳細情報: 既定のクラスファクトリと集計モデルを変更する'
title: 既定のクラスファクトリと集計モデルの変更
ms.date: 11/04/2016
helpviewer_keywords:
- CComClassFactory class, making the default
- aggregation [C++], using ATL
- aggregation [C++], aggregation models
- defaults [C++], aggregation model in ATL
- default class factory
- class factories, changing default
- CComCoClass class, default class factory and aggregation model
- default class factory, ATL
- defaults [C++], class factory
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
ms.openlocfilehash: b25dc1c2cf3378532f02b1c0d5ba56cd43ee4ae4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148279"
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>既定のクラスファクトリと集計モデルの変更

ATL では、 [CComCoClass](../atl/reference/ccomcoclass-class.md) を使用して、オブジェクトの既定のクラスファクトリと集計モデルを定義します。 `CComCoClass` 次の2つのマクロを指定します。

- [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory)[CComClassFactory](../atl/reference/ccomclassfactory-class.md)するクラスファクトリを宣言します。

- [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) オブジェクトを集計できることを宣言します。

クラス定義で別のマクロを指定することで、これらの既定値のいずれかをオーバーライドできます。 たとえば、の代わりに [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) を使用するには、 `CComClassFactory` [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) マクロを指定します。

[!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]

クラスファクトリを定義する他の2つのマクロは [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) および [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton)ます。

ATL では、 **`typedef`** 機構を使用して既定の動作を実装することもできます。 たとえば、DECLARE_AGGREGATABLE マクロはを使用して **`typedef`** 、という型を定義し `_CreatorClass` ます。この型は ATL 全体で参照されます。 派生クラスでは、 **`typedef`** 基底クラスのと同じ名前を使用していると、ATL が定義を使用し、既定の動作をオーバーライドすることに注意して **`typedef`** ください。

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)<br/>
[集計およびクラスファクトリマクロ](../atl/reference/aggregation-and-class-factory-macros.md)

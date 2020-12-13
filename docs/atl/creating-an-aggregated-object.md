---
description: 詳細については、「集計オブジェクトの作成」を参照してください。
title: 集計オブジェクトの作成
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
ms.openlocfilehash: e6efbf63e28d0477730a2d7c31ec91e9b75520e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153227"
---
# <a name="creating-an-aggregated-object"></a>集計オブジェクトの作成

集計デリゲートは `IUnknown` 、外部オブジェクトへのポインターを内部オブジェクトに提供する呼び出しを呼び出します `IUnknown` 。

## <a name="to-create-an-aggregated-object"></a>集計されたオブジェクトを作成するには

1. `IUnknown`クラスオブジェクトへのポインターを追加し、コンストラクターで NULL に初期化します。

1. [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct)をオーバーライドして、集計を作成します。

1. `IUnknown`手順 1. で定義したポインターを、 [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate)マクロの2番目のパラメーターとして使用します。

1. [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease)をオーバーライドしてポインターを解放し `IUnknown` ます。

> [!NOTE]
> の間に集約されたオブジェクトからインターフェイスを使用して解放する場合は `FinalConstruct` 、クラスオブジェクトの定義に [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) マクロを追加する必要があります。

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)

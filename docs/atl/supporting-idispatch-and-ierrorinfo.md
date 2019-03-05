---
title: IDispatch と IErrorInfo のサポート
ms.date: 11/04/2016
f1_keywords:
- IErrorInfo
- IDispatch
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
ms.openlocfilehash: aa3800b529238ba78cb3aacc555d1a1d7afb94ca
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290548"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch と IErrorInfo のサポート

テンプレート クラスを使用して[IDispatchImpl](../atl/reference/idispatchimpl-class.md)の既定の実装を提供する、`IDispatch Interface`オブジェクトの任意のデュアル インターフェイスの部分。

オブジェクトで使用する場合、`IErrorInfo`エラーは、クライアントにバックアップし、オブジェクトがサポートする必要がありますを報告するインターフェイス、`ISupportErrorInfo Interface`インターフェイス。 テンプレート クラスは、 [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md)オブジェクトでエラーを生成する 1 つのインターフェイスしかない場合は、これを実装する簡単な方法を提供します。

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)

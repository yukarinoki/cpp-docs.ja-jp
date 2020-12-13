---
description: 詳細については、「IDispatch と IErrorInfo のサポート」を参照してください。
title: IDispatch と IErrorInfo のサポート
ms.date: 11/04/2016
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
ms.openlocfilehash: 4622c8811fafc9512400345e5876dd24c466bc93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138451"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch と IErrorInfo のサポート

テンプレートクラス [IDispatchImpl](../atl/reference/idispatchimpl-class.md) を使用すると、 `IDispatch Interface` オブジェクトの任意のデュアルインターフェイスの部分の既定の実装を提供できます。

オブジェクトがインターフェイスを使用して `IErrorInfo` クライアントにエラーを報告する場合、オブジェクトはインターフェイスをサポートしている必要があり `ISupportErrorInfo Interface` ます。 テンプレートクラス [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) を使用すると、オブジェクトでエラーを生成するインターフェイスが1つしかない場合に、簡単に実装することができます。

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)

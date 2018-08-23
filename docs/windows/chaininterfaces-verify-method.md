---
title: Chaininterfaces::verify メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6dbc595714cbecf2ad13db13051866e31e5ebcd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42581059"
---
# <a name="chaininterfacesverify-method"></a>ChainInterfaces::Verify メソッド

各インターフェイスは、テンプレート パラメーターで定義されていることを確認します*I0*を通じて*I9*から継承`IUnknown`や`IInspectable`、および*I0*から継承。*I1*を通じて*I9*します。

## <a name="syntax"></a>構文

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

## <a name="remarks"></a>Remarks

検証操作に失敗した場合、 **static_assert**エラーを説明するエラー メッセージを出力します。

テンプレート パラメーター *I0*と*I1*が必要なパラメーターと*I2*を通じて*I9*は省略可能です。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)
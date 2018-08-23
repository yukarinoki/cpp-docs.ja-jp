---
title: Asyncbase::errorcode メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ErrorCode
dev_langs:
- C++
helpviewer_keywords:
- ErrorCode method
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7336824d04745440a1f6152ebacfed2afc62258e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602379"
---
# <a name="asyncbaseerrorcode-method"></a>AsyncBase::ErrorCode メソッド

現在の非同期操作のエラー コードを取得します。

## <a name="syntax"></a>構文

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>パラメーター

*error*  
この操作が現在のエラー コードを格納する場所です。

## <a name="remarks"></a>Remarks

この操作は、スレッド セーフです。

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[AsyncBase クラス](../windows/asyncbase-class.md)
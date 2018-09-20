---
title: Asyncbase::put_id メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::put_Id
dev_langs:
- C++
helpviewer_keywords:
- put_Id method
ms.assetid: aebad85f-4774-42de-b625-a9cf5f65cb4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 65d36c76ca05343084b709096d38014d802628c8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439004"
---
# <a name="asyncbaseputid-method"></a>AsyncBase::put_Id メソッド

非同期操作のハンドルを設定します。

## <a name="syntax"></a>構文

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>パラメーター

*ID*<br/>
0 以外のハンドル。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_INVALIDARG または E_ILLEGAL_METHOD_CALL します。

## <a name="requirements"></a>要件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[AsyncBase クラス](../windows/asyncbase-class.md)
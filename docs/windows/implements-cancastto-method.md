---
title: Implements::cancastto メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 328691877a3b129c852460f8f68cdd3db4974e6f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595300"
---
# <a name="implementscancastto-method"></a>Implements::CanCastTo メソッド

指定したインターフェイスへのポインターを取得します。

## <a name="syntax"></a>構文

```cpp
__forceinline HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>パラメーター

*riid*  
インターフェイス ID への参照

*ppv*  
かどうかは成功すると、インターフェイスへのポインターで指定された*riid*します。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、E_NOINTERFACE など、エラーを示す HRESULT。

## <a name="remarks"></a>Remarks

これは、QueryInterface 操作を実行する内部のヘルパー関数です。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Implements 構造体](../windows/implements-structure.md)
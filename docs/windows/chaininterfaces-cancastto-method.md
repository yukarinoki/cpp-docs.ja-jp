---
title: Chaininterfaces::cancastto メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8398f0bd4d9fdc786926782b13ebcac913a6a351
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612871"
---
# <a name="chaininterfacescancastto-method"></a>ChainInterfaces::CanCastTo メソッド

指定されたインターフェイス ID を既定以外のテンプレート パラメーターで定義された特殊な形式をそれぞれにキャストできるかどうかを示します。

## <a name="syntax"></a>構文

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>パラメーター

*riid*  
インターフェイス ID。

*ppv*  
正常にキャストされた最後のインターフェイス ID へのポインター。

## <a name="return-value"></a>戻り値

**true**すべてのキャスト操作が成功した場合、それ以外の場合**false**します。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)
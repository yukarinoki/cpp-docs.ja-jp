---
title: Hstring::getaddressof メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
dev_langs:
- C++
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e327e2818903396c154be7406ec325695b6b6982
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613366"
---
# <a name="hstringgetaddressof-method"></a>HString::GetAddressOf メソッド

基になる HSTRING ハンドルへのポインターを取得します。

## <a name="syntax"></a>構文

```cpp
HSTRING* GetAddressOf() throw()  
```

## <a name="return-value"></a>戻り値

基になる HSTRING ハンドルへのポインター。

## <a name="remarks"></a>Remarks

この操作の後は、基になる HSTRING ハンドルの文字列値が破棄されます。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HString クラス](../windows/hstring-class.md)
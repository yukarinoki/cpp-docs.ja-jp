---
title: Hstringreference::copyto メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 179d9b14-1ced-4b16-b297-19ca1e92a462
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 22886621760ed53649d26180877b1463ec2d3f2d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592165"
---
# <a name="hstringreferencecopyto-method"></a>HStringReference::CopyTo メソッド

現在のコピー **HStringReference**オブジェクトを HSTRING オブジェクトにします。

## <a name="syntax"></a>構文

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>パラメーター

*str*  
コピーを受信する HSTRING です。

## <a name="remarks"></a>Remarks

このメソッドは、 [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx)関数。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HStringReference クラス](../windows/hstringreference-class.md)
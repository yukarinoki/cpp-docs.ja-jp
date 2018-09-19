---
title: Safeintexception::safeintexception |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException, constructor
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 749ef965520732c37457613f44e0a23e213023db
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700974"
---
# <a name="safeintexceptionsafeintexception"></a>SafeIntException::SafeIntException

作成、 **SafeIntException**オブジェクト。

## <a name="syntax"></a>構文

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>パラメーター

*コード*<br/>
[in]発生したエラーを説明する列挙値。

## <a name="remarks"></a>Remarks

使用可能な値を*コード*Safeint.h ファイルで定義されます。 便宜上、使用可能な値も次に示します。

- `SafeIntNoError`

- `SafeIntArithmeticOverflow`

- `SafeIntDivideByZero`

## <a name="requirements"></a>要件

**ヘッダー:** safeint.h

**Namespace:** msl::utilities

## <a name="see-also"></a>関連項目

[SafeInt ライブラリ](../windows/safeint-library.md)  
[SafeIntException クラス](../windows/safeintexception-class.md)  
[SafeInt クラス](../windows/safeint-class.md)
---
title: SafeIntException クラス |Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException Class
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException class
- SafeIntException, constructor
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4ffd82f80b8af0b53ca86ca3daded84580e1e07b
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235738"
---
# <a name="safeintexception-class"></a>SafeIntException クラス

`SafeInt`クラスで使用`SafeIntException`数学的な操作が完了できない理由を特定します。

## <a name="syntax"></a>構文

```cpp
class SafeIntException;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                    | 説明
------------------------------------------------------- | ------------------------------------
[SafeIntException::SafeIntException](#safeintexception) | `SafeIntException` オブジェクトを作成します。

## <a name="remarks"></a>Remarks

[SafeInt クラス](../windows/safeint-class.md)唯一のクラスを使用するには、`SafeIntException`クラス。

## <a name="inheritance-hierarchy"></a>継承階層

`SafeIntException`

## <a name="requirements"></a>要件

**ヘッダー:** safeint.h

**Namespace:** msl::utilities

## <a name="safeintexception"></a>Safeintexception::safeintexception

`SafeIntException` オブジェクトを作成します。

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>パラメーター

*コード*<br/>
[in]発生したエラーを説明する列挙値。

### <a name="remarks"></a>Remarks

使用可能な値を*コード*Safeint.h ファイルで定義されます。 便宜上、使用可能な値も次に示します。

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`

---
title: SafeIntException クラス
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeIntException Class
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
helpviewer_keywords:
- SafeIntException class
- SafeIntException, constructor
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
ms.openlocfilehash: 80a1573c2f43b1f4b31731083974f87ba389fac2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566661"
---
# <a name="safeintexception-class"></a>SafeIntException クラス

`SafeInt`クラスで使用`SafeIntException`数学的な操作が完了できない理由を特定します。

> [!NOTE]
> このライブラリの最新バージョンは[ https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt)します。

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

## <a name="requirements"></a>必要条件

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

*code*<br/>
[in]発生したエラーを説明する列挙値。

### <a name="remarks"></a>Remarks

使用可能な値を*コード*Safeint.h ファイルで定義されます。 便宜上、使用可能な値も次に示します。

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`

---
description: '詳細情報: SafeIntException クラス'
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
ms.openlocfilehash: 6a7be21b0dfa42a23ba60eac7eb3f4ebbf1629ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149579"
---
# <a name="safeintexception-class"></a>SafeIntException クラス

`SafeInt` クラスでは、数学演算を完了できない理由を特定するために `SafeIntException` を使用します。

> [!NOTE]
> このライブラリの最新バージョンは、にあり [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) ます。

## <a name="syntax"></a>構文

```cpp
class SafeIntException;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                    | 説明
------------------------------------------------------- | ------------------------------------
[SafeIntException:: SafeIntException](#safeintexception) | `SafeIntException` オブジェクトを作成します。

## <a name="remarks"></a>解説

[SafeInt クラス](safeint-class.md)は、`SafeIntException` クラスを使用する唯一のクラスです。

## <a name="inheritance-hierarchy"></a>継承階層

`SafeIntException`

## <a name="requirements"></a>要件

**ヘッダー:** safeint.h

**名前空間:** msl::utilities

## <a name="safeintexceptionsafeintexception"></a><a name="safeintexception"></a> SafeIntException:: SafeIntException

`SafeIntException` オブジェクトを作成します。

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>パラメーター

*code*<br/>
[in] 発生したエラーを説明する列挙データ値。

### <a name="remarks"></a>解説

*code* に使用できる値は、Safeint.h ファイルに定義されています。 参考までに、使用できる値を次に示します。

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`

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
ms.openlocfilehash: e118d7e3cce47ebb93cef16319a8fc45aab1118b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349948"
---
# <a name="safeintexception-class"></a>SafeIntException クラス

`SafeInt` クラスでは、数学演算を完了できない理由を特定するために `SafeIntException` を使用します。

> [!NOTE]
> このライブラリの最新バージョンは に[https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt)にあります。

## <a name="syntax"></a>構文

```cpp
class SafeIntException;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                    | 説明
------------------------------------------------------- | ------------------------------------
[セーフイント例外::セーフイント例外](#safeintexception) | `SafeIntException` オブジェクトを作成します。

## <a name="remarks"></a>解説

[SafeInt クラス](../safeint/safeint-class.md)は、`SafeIntException` クラスを使用する唯一のクラスです。

## <a name="inheritance-hierarchy"></a>継承階層

`SafeIntException`

## <a name="requirements"></a>必要条件

**ヘッダー:** safeint.h

**名前空間:** msl::utilities

## <a name="safeintexceptionsafeintexception"></a><a name="safeintexception"></a>セーフイント例外::セーフイント例外

`SafeIntException` オブジェクトを作成します。

```cpp
SafeIntException();

SafeIntException(
   SafeIntError code
);
```

### <a name="parameters"></a>パラメーター

*コード*<br/>
[in] 発生したエラーを説明する列挙データ値。

### <a name="remarks"></a>解説

*code* に使用できる値は、Safeint.h ファイルに定義されています。 参考までに、使用できる値を次に示します。

- `SafeIntNoError`
- `SafeIntArithmeticOverflow`
- `SafeIntDivideByZero`

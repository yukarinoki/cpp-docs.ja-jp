---
description: '詳細情報: DontUseNewUseMake クラス'
title: DontUseNewUseMake クラス
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
helpviewer_keywords:
- Microsoft::WRL::Details::DontUseNewUseMake class
- Microsoft::WRL::Details::DontUseNewUseMake::operator new operator
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
ms.openlocfilehash: f6b6740e472123e59565e3bad16e4a535a4e17fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272904"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake クラス

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>解説

で演算子を使用できないよう `new` に `RuntimeClass` します。 そのため、代わりに [Make 関数](make-function.md) を使用する必要があります。

## <a name="members"></a>メンバー

### <a name="public-operators"></a>パブリック演算子

名前                                             | 説明
------------------------------------------------ | ---------------------------------------------------------------------------
[DontUseNewUseMake:: operator new](#operator-new) | オーバーロード演算子 `new` は、で使用されないようにし `RuntimeClass` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`DontUseNewUseMake`

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft:: WRL::D etails

## <a name="dontusenewusemakeoperator-new"></a><a name="operator-new"></a> DontUseNewUseMake:: operator new

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>パラメーター

*__unnamed0*<br/>
割り当てるメモリのバイト数を指定する無名のパラメーター。

*場所*<br/>
割り当てられる型。

### <a name="return-value"></a>戻り値

演算子をオーバーロードする場合に、追加の引数を渡す方法を提供 `new` します。

### <a name="remarks"></a>解説

オーバーロード演算子 `new` は、で使用されないようにし `RuntimeClass` ます。

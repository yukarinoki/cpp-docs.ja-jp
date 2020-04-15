---
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
ms.openlocfilehash: ae67373b4f2f2d4a199b939b06e6f526f1365446
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371554"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake クラス

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>解説

で`new``RuntimeClass`演算子を使用できないようにします。 したがって[、Make 関数](make-function.md)を代わりに使用する必要があります。

## <a name="members"></a>メンバー

### <a name="public-operators"></a>パブリック演算子

名前                                             | 説明
------------------------------------------------ | ---------------------------------------------------------------------------
[新しい操作を行う::演算子が新しい](#operator-new) | 演算子`new`をオーバーロードし、 で`RuntimeClass`使用されないようにします。

## <a name="inheritance-hierarchy"></a>継承階層

`DontUseNewUseMake`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="dontusenewusemakeoperator-new"></a><a name="operator-new"></a>新しい操作を行う::演算子が新しい

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>パラメーター

*__unnamed0*<br/>
割り当てるメモリのバイト数を指定する名前のないパラメーター。

*配置*<br/>
割り当てる型。

### <a name="return-value"></a>戻り値

演算子`new`をオーバーロードする場合に、追加の引数を渡す方法を提供します。

### <a name="remarks"></a>解説

演算子`new`をオーバーロードし、 で`RuntimeClass`使用されないようにします。

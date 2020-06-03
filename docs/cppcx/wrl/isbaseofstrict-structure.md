---
title: IsBaseOfStrict 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
ms.openlocfilehash: 71db5a1b52a7d7d5471c15591fb34d954b465d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371354"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>パラメーター

*ベース*<br/>
基本データ型。

*派生*<br/>
派生型。

## <a name="remarks"></a>解説

一方の型がもう一方の型の基本クラスであるかどうかをテストします。

最初のテンプレートは、型が基本型から派生しているかどうかを**テストします。** **true** 2 番目のテンプレートは、型がそれ自体から派生しているかどうかをテスト**します。**

## <a name="members"></a>メンバー

### <a name="public-constants"></a>パブリック定数

名前                            | 説明
------------------------------- | --------------------------------------------------
[ストベースオブストリクスト::値](#value) | ある型が別の型のベースであるかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`IsBaseOfStrict`

## <a name="requirements"></a>必要条件

**ヘッダー:** 内部.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="isbaseofstrictvalue"></a><a name="value"></a>ストベースオブストリクスト::値

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>解説

ある型が別の型のベースであるかどうかを示します。

`value`型`Base`が型`Derived`の基本クラスの場合は**true、** それ以外の場合は**false**です。

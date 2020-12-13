---
description: '詳細情報: nothrow_t 構造'
title: nothrow_t 構造体
ms.date: 11/04/2016
f1_keywords:
- nothrow_t
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
ms.openlocfilehash: 974fbe3a1e27da41c6366c62d748426293a54437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338097"
---
# <a name="nothrow_t-structure"></a>nothrow_t 構造体

この構造体は operator new の関数パラメーターとして使用し、関数に対して、割り当て失敗を報告する際に例外をスローするのではなく Null ポインター を返すように指定します。

## <a name="syntax"></a>構文

```cpp
struct std::nothrow_t {};
```

## <a name="remarks"></a>解説

この構造体により、コンパイラが適切なバージョンのコンストラクターを選択できます。 [nothrow](../standard-library/new-functions.md#nothrow) は、`std::nothrow_t` 型のオブジェクトと同義です。

## <a name="example"></a>例

`std::nothrow_t` を関数パラメーターとして使用する方法の例については、[operator new](../standard-library/new-operators.md#op_new) および [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr) に関する記事をご覧ください。

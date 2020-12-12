---
description: '詳細情報: bad_exception クラス'
title: bad_exception クラス
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 6b47facc751e1f16e033f26be284db1287e79ea8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321613"
---
# <a name="bad_exception-class"></a>bad_exception クラス

このクラスは、予期しないハンドラーからスローされる例外を記述します。

## <a name="syntax"></a>構文

```cpp
class bad_exception : public exception {};

bad_exception();
bad_exception(const bad_exception&);
bad_exception& operator=(const bad_exception&);
const char* what() const override;
```

## <a name="remarks"></a>解説

[unexpected](../standard-library/exception-functions.md#unexpected) は、`bad_exception` が関数のスロー リストに含まれている場合には、終了の代わりに、または [set_unexpected](../standard-library/exception-functions.md#set_unexpected) で指定された別の関数を呼び出す代わりに、`bad_exception` をスローします。

によって返される値 `what` は、実装定義の C 文字列です。 このメンバー関数は、いずれも例外をスローしません。

`bad_exception` クラスで継承されたメンバーの一覧については、「[exception クラス](../standard-library/exception-class.md)」を参照してください。

## <a name="example"></a>例

`bad_exception` をスローする [unexpected](../standard-library/exception-functions.md#unexpected) の使用例については、「[set_unexpected](../standard-library/exception-functions.md#set_unexpected)」を参照してください。

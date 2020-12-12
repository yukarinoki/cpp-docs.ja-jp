---
description: '詳細情報: exception クラス'
title: exception クラス
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
ms.openlocfilehash: a2061a2609017872145b12b4863e939788a123cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324450"
---
# <a name="exception-class"></a>exception クラス

このクラスは、特定の式と C++ 標準ライブラリによってスローされたすべての例外の基底クラスとして機能します。

## <a name="syntax"></a>構文

```cpp
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
};
```

## <a name="remarks"></a>解説

具体的には、この基本クラスは、で定義されている標準の例外クラスのルートです [\<stdexcept>](../standard-library/stdexcept.md) 。 `what` によって返される C の文字列値は、既定のコンストラクターによって未指定のまま残されますが、特定の派生クラスのコンストラクターによって実装定義された C の文字列として定義される場合があります。 このメンバー関数は、いずれも例外をスローしません。

**`int`** パラメーターを使用すると、メモリを割り当てる必要がないことを指定できます。 の値 **`int`** は無視されます。

> [!NOTE]
> コンストラクター `exception(const char* const &message)` と `exception(const char* const &message, int)` は、C++ 標準ライブラリに対する Microsoft 拡張機能です。

## <a name="example"></a>例

クラスを継承する標準の例外クラスの使用例については、 `exception` 「」で定義されているクラスを参照してください [\<stdexcept>](../standard-library/stdexcept.md) 。

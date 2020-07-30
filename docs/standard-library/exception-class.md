---
title: exception クラス
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
ms.openlocfilehash: fd3fb3c48e9501b7aaf90bca14ea98530b245ec0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228272"
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

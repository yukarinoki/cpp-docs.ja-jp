---
description: '詳細情報: 変更可能なデータメンバー (C++)'
title: 変更可能なデータ メンバー (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: a288b382b456fa313c49832bd2d13aaceb269be9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313815"
---
# <a name="mutable-data-members-c"></a>変更可能なデータ メンバー (C++)

このキーワードは、クラスの non-static データ メンバーおよび non-const データ メンバーにのみ適用できます。 データメンバーが宣言されている場合は **`mutable`** 、メンバー関数からこのデータメンバーに値を割り当てることが **`const`** できます。

## <a name="syntax"></a>構文

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>解説

たとえば、次のコードは、がとして宣言されているため、エラーなしでコンパイルされ `m_accessCount` **`mutable`** ます。したがって、 `GetFlag` が const メンバー関数であっても、によって変更でき `GetFlag` ます。

```cpp
// mutable.cpp
class X
{
public:
   bool GetFlag() const
   {
      m_accessCount++;
      return m_flag;
   }
private:
   bool m_flag;
   mutable int m_accessCount;
};

int main()
{
}
```

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)

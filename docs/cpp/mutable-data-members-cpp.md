---
title: 変更可能なデータ メンバー (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de0a208341e6a687d1319c4d8d60cc8671555dd6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107001"
---
# <a name="mutable-data-members-c"></a>変更可能なデータ メンバー (C++)

このキーワードは、クラスの non-static データ メンバーおよび non-const データ メンバーにのみ適用できます。 データ メンバーが宣言されている場合**変更可能な**からこのデータ メンバーに値を代入することはその後、 **const**メンバー関数。

## <a name="syntax"></a>構文

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>Remarks

に次のコードがエラーなくコンパイルするなど、`m_accessCount`するとして宣言されている**変更可能な**で変更することができます`GetFlag`にもかかわらず`GetFlag`が const メンバー関数。

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
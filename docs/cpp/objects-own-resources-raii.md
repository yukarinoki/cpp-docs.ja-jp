---
title: 所有するオブジェクト (RAII) のリソース |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 724944028c7343d6b85cf61bde810afcbf1c9619
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136011"
---
# <a name="objects-own-resources-raii"></a>リソースを所有するオブジェクト (RAII)

独自のリソース オブジェクトを確認します。 この原則とも呼ばれます"resource acquisition is 初期化"または"RAII"。

## <a name="example"></a>例

(ほとんどの場合に unique_ptr) それを所有する別の名前付きオブジェクトをコンス トラクター引数としてすべての「新しい」オブジェクトを渡します。

```cpp
void f() {
    unique_ptr<widget> p( new widget() );
    my_class x( new widget() );
    // ...
} // automatic destruction and deallocation for both widget objects
  // automatic exception safety, as if "finally { p->dispose(); x.w.dispose(); }"
```

常にすぐに、新しいリソースを所有する別のオブジェクトに渡します。

```cpp
void g() {
    other_class y( OpenFile() );
    // ...
} // automatic closing and release for file resource
  // automatic exception safety, as if "finally { y.file.dispose(); }"
```

## <a name="see-also"></a>関連項目

[C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)
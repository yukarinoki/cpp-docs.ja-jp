---
title: オブジェクト (RAII) のリソースを所有して |Microsoft ドキュメント
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
ms.openlocfilehash: dfd3f1df54e5b5881ed15efeb98a6e6070f400a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419934"
---
# <a name="objects-own-resources-raii"></a>リソースを所有するオブジェクト (RAII)
独自のリソース オブジェクトを確認します。 この原則とも呼ばれる"resource acquisition is 初期化"または"RAII"。  
  
## <a name="example"></a>例  
 コンス トラクターの引数として (unique_ptr ほとんどの場合) を所有する別の名前付きオブジェクトのすべての「新規」オブジェクトを渡します。  
  
```cpp  
void f() {  
    unique_ptr<widget> p( new widget() );  
    my_class x( new widget() );  
    // ...  
} // automatic destruction and deallocation for both widget objects  
  // automatic exception safety, as if "finally { p->dispose(); x.w.dispose(); }"  
```  
  
 常にすぐに所有されている別のオブジェクトを新しいリソースを渡します。  
  
```cpp  
void g() {  
    other_class y( OpenFile() );  
    // ...  
} // automatic closing and release for file resource  
  // automatic exception safety, as if "finally { y.file.dispose(); }"  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)
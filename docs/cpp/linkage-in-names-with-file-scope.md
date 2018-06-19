---
title: ファイル スコープを持つ名前にあるリンケージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- static modifier, file scope
- static names and file scope
- file scope [C++]
- declarations [C++], external
- external linkage, scope linkage rules
- static variables, external declarations
ms.assetid: 38d3fa5e-1861-466e-a590-84b86f7b184e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 770b30516d16cf9ffccaae4724b368ca8fa33be0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419782"
---
# <a name="linkage-in-names-with-file-scope"></a>ファイル スコープを持つ名前にあるリンケージ
次のリンケージ規則は、ファイル スコープを持つ名前 (`typedef` と列挙子の名前以外) に適用されます。  
  
-   名前として明示的に宣言されている場合**静的**、内部リンケージを持ち、独自の翻訳単位内のプログラム要素を識別します。  
  
-   列挙子名と `typedef` 名はリンケージを持ちません。  
  
-   ファイル スコープを持つ他のすべての名前は外部リンケージを持ちます。  
  
 **Microsoft 固有の仕様**  
  
-   ファイル スコープを持つ関数名が明示的に宣言されているとして**インライン**がインスタンス化されるか、そのアドレスが参照されている場合、外部リンケージがあります。 したがって、ファイル スコープを持つ関数は内部または外部リンケージを持つことができます。  
  
 **Microsoft 固有の仕様はここまで**  
  
 次の場合、クラスは内部リンケージを持ちます。  
  
-   C++ の機能を使用していません (たとえば、メンバー アクセス制御、メンバー関数、コンストラクター、デストラクターなど)。  
  
-   外部リンケージを持つ別の名前の宣言で使用されていません。 この制約は、外部リンケージを持つ関数に渡されるクラス型のオブジェクトにより、クラスが外部リンケージを持つことを意味します。  
  
## <a name="see-also"></a>関連項目  
 [プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)
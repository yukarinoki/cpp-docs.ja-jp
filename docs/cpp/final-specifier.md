---
title: final 指定子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- final_CPP
dev_langs:
- C++
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f28ae7b7cb8bdcf335757c58d5e744974f4c7cad
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405958"
---
# <a name="final-specifier"></a>final 指定子
使用することができます、**最終的な**キーワードを派生クラスでオーバーライドできない仮想関数を指定します。 また、このキーワードは、継承できないクラスの指定にも使用できます。  
  
## <a name="syntax"></a>構文  
  
```  
function-declaration final;  
class class-name final base-classes  
```  
  
## <a name="remarks"></a>Remarks  
 **最終的な**は状況依存と予約済みキーワードではありません関数宣言の後に使用されますか、クラスの名前。 それ以外の場合、だけに特別な意味を持ちます。  
  
 ときに**最終的な**クラスの宣言で使用される、`base-classes`宣言の省略可能な部分です。  
  
## <a name="example"></a>例  
 次の例では、**最終的な**仮想関数をオーバーライドできないことを指定するキーワード。  
  
```cpp  
class BaseClass  
{  
    virtual void func() final;  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void func(); // compiler error: attempting to   
                         // override a final function  
};  
```  
  
 メンバー関数をオーバーライドできることを指定する方法については、次を参照してください。[オーバーライド指定子](../cpp/override-specifier.md)します。  
  
 次の例では、**最終**クラスを継承できないことを指定するキーワード。  
  
```cpp  
class BaseClass final   
{  
};  
  
class DerivedClass: public BaseClass // compiler error: BaseClass is   
                                     // marked as non-inheritable  
{  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [override 指定子](../cpp/override-specifier.md)
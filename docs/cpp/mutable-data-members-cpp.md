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
ms.openlocfilehash: 65d2fc42021a01a1260b57f9516e53c439c8e604
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943882"
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
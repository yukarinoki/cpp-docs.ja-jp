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
ms.openlocfilehash: adc8f9c456d28089d57bc1f13b61ad8efa10b6b6
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402921"
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
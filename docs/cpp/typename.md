---
title: typename |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- typename_cpp
dev_langs:
- C++
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79ba7d0bda73762d04f0dd11668eb31c275ac03f
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467930"
---
# <a name="typename"></a>typename
テンプレートの定義で、不明な識別子が型であるコンパイラに対するヒントを提供します。 テンプレート パラメーター リストでは、型パラメーターを指定に使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
typename identifier;  
```  
  
## <a name="remarks"></a>Remarks  
 テンプレート定義内の名前がテンプレート引数に依存する修飾名である場合、このキーワードを使用する必要があります。修飾名に依存しない場合は省略可能です。 詳細については、次を参照してください。[テンプレートと名前解決](../cpp/templates-and-name-resolution.md)します。  
  
 **typename**任意の型定義またはテンプレート宣言の任意の場所で使用できます。 テンプレート基底クラスへのテンプレート引数として使用する場合を除いて、このキーワードを基底クラス リストで使用することはできません。  
  
```cpp 
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 **Typename**の代わりにキーワードを使用することも**クラス**テンプレート パラメーターの一覧表示されます。 たとえば、次のステートメントと同じ意味です。  
  
```cpp 
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## <a name="example"></a>例  
  
```cpp 
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [テンプレート](../cpp/templates-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)
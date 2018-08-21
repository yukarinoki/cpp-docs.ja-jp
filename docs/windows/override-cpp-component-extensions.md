---
title: override (C++ コンポーネント拡張) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 855f2c18423fd6c1ca708034214e6f5c7048d6d8
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605562"
---
# <a name="override--c-component-extensions"></a>override (C++ コンポーネント拡張)
**オーバーライド**状況依存のキーワードは、型のメンバーが基底クラスまたは基本インターフェイスのメンバーをオーバーライドすることを示します。  
  
## <a name="remarks"></a>Remarks  
 **オーバーライド**キーワードは、ネイティブ ターゲット (既定のコンパイラ オプション) をコンパイルするときに有効な Windows ランタイム ターゲット (`/ZW`コンパイラ オプション)、または共通言語ランタイム ターゲット (`/clr`コンパイラ オプション)。  
  
 オーバーライド指定子の詳細については、次を参照してください。[オーバーライド指定子](../cpp/override-specifier.md)と[オーバーライド指定子とネイティブ コンパイル](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)します。  
  
 状況依存のキーワードの詳細については、次を参照してください。[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)します。  
  
## <a name="examples"></a>使用例  
  
 コード例を次に示します**オーバーライド**ネイティブ コンパイルでも使用できます。  
  
```cpp  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
### <a name="example"></a>例

 コード例を次に示します**オーバーライド**Windows ランタイム コンパイルで使用できます。  
  
```cpp 
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
#### <a name="requirements"></a>要件  
  
 コンパイラ オプション: `/ZW`  
    
### <a name="example"></a>例

 コード例を次に示します**オーバーライド**共通言語ランタイム コンパイルで使用できます。  
  
```cpp  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
#### <a name="requirements"></a>要件  
  
 コンパイラ オプション: `/clr`  
  
## <a name="see-also"></a>関連項目  
 [オーバーライド指定子](../cpp/override-specifier.md)   
 [オーバーライド指定子](../windows/override-specifiers-cpp-component-extensions.md)
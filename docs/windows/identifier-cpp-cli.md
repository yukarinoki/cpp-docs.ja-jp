---
title: _ _identifier (c +/cli CLI) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
dev_langs:
- C++
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6eac892da91c5f3640bdd243a0b3c6525faa5c2a
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603346"
---
# <a name="identifier-ccli"></a>__identifier (C++/CLI)
識別子としての Visual C のキーワードを使用できるようにします。  
  
## <a name="all-platforms"></a>すべてのプラットフォーム  
### <a name="syntax"></a>構文  
  
```  
__identifier(  
Visual_C++_keyword  
)  
```  
  
### <a name="remarks"></a>Remarks  
  
使用、 **_ _identifier**キーワードではない識別子のキーワードは許可されていますが、スタイルの問題としてお勧めします。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: `/ZW`  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次の例では、クラスが名前付き`template`c# で作成され、DLL として配布されます。 使用する Visual C プログラムで、`template`クラス、 **_ _identifier**キーワードという事実を非表示にする**テンプレート**は標準の C++ キーワードです。  
  
```cs  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```cpp  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
### <a name="remarks"></a>Remarks  
  
 **_ _Identifier**キーワードが有効では、`/clr`コンパイラ オプション。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: `/clr`  
  
### <a name="examples"></a>使用例  
  
 次の例では、クラスが名前付き`template`c# で作成され、DLL として配布されます。 使用する Visual C プログラムで、`template`クラス、 **_ _identifier**キーワードという事実を非表示にする**テンプレート**は標準の C++ キーワードです。  
  
```cs  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```cpp  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)
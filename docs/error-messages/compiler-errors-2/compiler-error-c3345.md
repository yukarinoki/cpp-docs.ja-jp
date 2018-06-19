---
title: コンパイラ エラー C3345 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3345
dev_langs:
- C++
helpviewer_keywords:
- C3345
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e6b3a021d9c747e4ec30278d8a22bde899cb39a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254236"
---
# <a name="compiler-error-c3345"></a>コンパイラ エラー C3345
'identifier': モジュール名に対する無効な識別子です  
  
 モジュールの *識別子* に 1 つまたは複数の無効な文字が含まれています。 識別子は、最初の文字がアルファベット、アンダースコア、または高位 ANSI (0x80-FF) 文字で、それ以降の任意の文字が英数字、アンダースコア、または高位 ANSI 文字である場合に有効です。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  *識別子* に空白またはその他の無効な文字が含まれていないことを確認します。  
  
## <a name="example"></a>例  
 次のコード例では、 `name` 属性の `module` パラメーターに空白が含まれているので、エラー メッセージ C3345 が発生します。  
  
```  
// cpp_attr_name_module.cpp  
// compile with: /LD /link /OPT:NOREF  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
// C3345 expected  
[module(dll, name="My Library", version="1.2", helpfile="MyHelpFile")]   
// Try the following line instead  
//[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]   
// Module attribute now applies to this class  
class CMyClass {  
public:  
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {  
   // add your own code here  
   return __super::DllMain(dwReason, lpReserved);  
   }  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [__iscsym](../../c-runtime-library/reference/iscsym-functions.md)   
 [文字分類](../../c-runtime-library/character-classification.md)   
 [モジュール](../../windows/module-cpp.md)
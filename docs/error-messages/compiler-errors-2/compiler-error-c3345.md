---
title: コンパイラ エラー C3345
ms.date: 11/04/2016
f1_keywords:
- C3345
helpviewer_keywords:
- C3345
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
ms.openlocfilehash: eb1d15a12bfebbf44f7335a848d68c367c285586
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027558"
---
# <a name="compiler-error-c3345"></a>コンパイラ エラー C3345

'identifier': モジュール名に対する無効な識別子です

モジュールの *識別子* に 1 つまたは複数の無効な文字が含まれています。 識別子は、最初の文字がアルファベット、アンダースコア、または高位 ANSI (0x80-FF) 文字で、それ以降の任意の文字が英数字、アンダースコア、または高位 ANSI 文字である場合に有効です。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. *識別子* に空白またはその他の無効な文字が含まれていないことを確認します。

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

[__iscsym](../../c-runtime-library/reference/iscsym-functions.md)<br/>
[文字分類](../../c-runtime-library/character-classification.md)<br/>
[module](../../windows/module-cpp.md)
---
description: 詳細については、「コンパイラエラー C3345」を参照してください。
title: コンパイラ エラー C3345
ms.date: 11/04/2016
f1_keywords:
- C3345
helpviewer_keywords:
- C3345
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
ms.openlocfilehash: 3e9fba1d24219d8ae3a0dee8488d36dc53557f09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337281"
---
# <a name="compiler-error-c3345"></a>コンパイラ エラー C3345

'identifier': モジュール名に対する無効な識別子です

モジュールの *識別子* に 1 つまたは複数の無効な文字が含まれています。 識別子は、最初の文字がアルファベット、アンダースコア、または高位 ANSI (0x80-FF) 文字で、それ以降の任意の文字が英数字、アンダースコア、または高位 ANSI 文字である場合に有効です。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. *識別子* に空白またはその他の無効な文字が含まれていないことを確認します。

## <a name="example"></a>例

次のコード例では、 `name` 属性の `module` パラメーターに空白が含まれているので、エラー メッセージ C3345 が発生します。

```cpp
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
[第](../../windows/attributes/module-cpp.md)

---
description: '詳細については、次を参照してください: _SCL_SECURE_NO_WARNINGS'
title: _SCL_SECURE_NO_WARNINGS
ms.date: 11/04/2016
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
ms.openlocfilehash: 383aeed0bdedc4830076248100c8cf0a1acf34b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187924"
---
# <a name="_scl_secure_no_warnings"></a>_SCL_SECURE_NO_WARNINGS

C++ 標準ライブラリの安全でない可能性のあるメソッドを呼び出すと、 [コンパイラの警告 (レベル 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)が生成されます。 この警告を無効にするには、コードでマクロ _SCL_SECURE_NO_WARNINGS を定義します。

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

プリコンパイル済みヘッダーを使用する場合は、C ランタイムライブラリまたは標準ライブラリヘッダーを含める前に、このディレクティブをプリコンパイル済みヘッダーファイルに配置します。 プリコンパイル済みヘッダーファイルをインクルードする前に個々のソースコードファイルに配置すると、コンパイラによって無視されます。

## <a name="remarks"></a>解説

警告 C4996 を無効にするその他の方法は、次のとおりです。

- [/D (プリプロセッサの定義)](../build/reference/d-preprocessor-definitions.md) コンパイラ オプションの使用:

   > cl/D_SCL_SECURE_NO_WARNINGS [その他のコンパイラオプション] myfile.txt

- [/w](../build/reference/compiler-option-warning-level.md) コンパイラ オプションの使用:

   > cl/wd4996 [その他のコンパイラオプション] myfile.txt

- [#pragma 警告](../preprocessor/warning.md) ディレクティブの使用:

   ```cpp
   #pragma warning(disable:4996)
   ```

また、警告 C4996 のレベルを **/w \<l> \<n>** コンパイラオプションで手動で変更することもできます。 たとえば、警告 C4996 をレベル 4 に設定します。

> cl/w44996 [その他のコンパイラオプション] myfile.txt

詳細については、「[/w、/W0、/W1、/W2、/W3、/W4, /w1, /w2, /w3、/w4、/Wall、/wd、/we、/wo、/Wv、/WX (警告レベル)](../build/reference/compiler-option-warning-level.md)」を参照してください。

## <a name="see-also"></a>関連項目

[安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)

---
title: _SCL_SECURE_NO_WARNINGS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
dev_langs:
- C++
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec02ce5aab3d8a7f95ec9020fe3e2a00c1f5bef7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854354"
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS

C++ 標準ライブラリで安全でないメソッドのいずれかの呼び出しの結果[コンパイラの警告 (レベル 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)です。 この警告を無効にするには、コードでマクロ **_SCL_SECURE_NO_WARNINGS** を定義します。

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

プリコンパイル済みヘッダーを使用する場合は、任意の C ランタイム ライブラリまたは標準ライブラリのヘッダーをインクルードする前に、このディレクティブをプリコンパイル済みヘッダー ファイル内に配置します。 配置した場合は、個々 のソース コード ファイルでプリコンパイル済みヘッダー ファイルをインクルードする前に、コンパイラによって無視されます。

## <a name="remarks"></a>コメント

警告 C4996 を無効にするその他の方法は、次のとおりです。

- [/D (プリプロセッサの定義)](../build/reference/d-preprocessor-definitions.md) コンパイラ オプションの使用:

   > cl/D_SCL_SECURE_NO_WARNINGS [他のコンパイラ オプション] myfile.cpp

- [/w](../build/reference/compiler-option-warning-level.md) コンパイラ オプションの使用:

   > cl/wd4996 [他のコンパイラ オプション] myfile.cpp

- [#pragma 警告](../preprocessor/warning.md) ディレクティブの使用:

   ```cpp
   #pragma warning(disable:4996)
   ```

また、**/w\<l>\<n>** コンパイラ オプションを使用して、警告 C4996 のレベルを手動で変更できます。 たとえば、警告 C4996 をレベル 4 に設定します。

> cl/w44996 [他のコンパイラ オプション] myfile.cpp

詳細については、「[/w、/W0、/W1、/W2、/W3、/W4, /w1, /w2, /w3、/w4、/Wall、/wd、/we、/wo、/Wv、/WX (警告レベル)](../build/reference/compiler-option-warning-level.md)」を参照してください。

## <a name="see-also"></a>関連項目

[安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)<br/>

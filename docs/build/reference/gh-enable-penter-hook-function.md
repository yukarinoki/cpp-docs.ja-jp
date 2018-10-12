---
title: -Gh (_penter フック関数の有効化) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _penter
dev_langs:
- C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 608472f3133464137d2d0f96128453e4239b16a2
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162088"
---
# <a name="gh-enable-penter-hook-function"></a>/Gh (_penter フック関数の有効化)

呼び出し、`_penter`すべてのメソッドまたは関数の開始時の関数。

## <a name="syntax"></a>構文

```
/Gh
```

## <a name="remarks"></a>Remarks

`_penter`関数は、任意のライブラリの一部ではないの定義を提供するかどうかは`_penter`します。

明示的に呼び出す予定がない限り`_penter`プロトタイプを提供する必要はありません。 関数は、次のプロトタイプがあった場合とおよびエントリのすべてのレジスタのコンテンツをプッシュし、終了時に変更されていないコンテンツを表示にする必要がありますに記述する必要があります。

```
void __declspec(naked) __cdecl _penter( void );
```

この宣言は、64 ビットのプロジェクトで使用可能ではありません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="example"></a>例

コンパイルした場合、次のコード **/Gh**、表示方法`_penter`2 回; と呼ばれる関数を入力するときに 1 回`main`関数を入力するときに 1 回`x`。

```cpp
// Gh_compiler_option.cpp
// compile with: /Gh
// processor: x86
#include <stdio.h>
void x() {}

int main() {
   x();
}

extern "C" void __declspec(naked) __cdecl _penter( void ) {
   _asm {
      push eax
      push ebx
      push ecx
      push edx
      push ebp
      push edi
      push esi
    }

   printf_s("\nIn a function!");

   _asm {
      pop esi
      pop edi
      pop ebp
      pop edx
      pop ecx
      pop ebx
      pop eax
      ret
    }
}
```

```Output
In a function!
In a function!
```

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
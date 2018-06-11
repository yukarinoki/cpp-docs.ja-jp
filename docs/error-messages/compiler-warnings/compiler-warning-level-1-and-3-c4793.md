---
title: コンパイラの警告 (レベル 1 および 3) C4793 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4793
dev_langs:
- C++
helpviewer_keywords:
- C6634
- C6635
- C6640
- C6630
- C6639
- C6636
- C6638
- C6631
- C6637
- C4793
ms.assetid: 819ada53-1d9c-49b8-a629-baf8c12314e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3942d09e823fc6bd2f370a8c8ee72b8d00e9a98
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704933"
---
# <a name="compiler-warning-level-1-and-3-c4793"></a>コンパイラの警告 (レベル 1 および 3) C4793

> '*関数*': 関数がネイティブ コードとしてコンパイルされます:'*理由*'

## <a name="remarks"></a>コメント

コンパイラがコンパイルできません。*関数*をマネージ コードにも、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプションを指定します。 代わりに、コンパイラの警告 C4793 と、継続タスクを説明メッセージを生成し、コンパイル*関数*をネイティブ コードにします。 継続タスクをメッセージに含まれる、*理由*理由を説明するテキスト*関数*をコンパイルできません`MSIL`です。

これは、レベル 1 の警告を指定すると、 **/clr: 純粋な**コンパイラ オプション。  **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

次の表は、可能な継続タスクのすべてのメッセージを一覧表示します。

|理由メッセージ|コメント|
|--------------------|-------------|
|整列データ型はマネージ コードではサポートされていません|CLR できる必要があります、必要に応じて、データを割り当てる場合に、データがなどの宣言と一致しない可能性もある[_ _m128](../../cpp/m128.md)または[整列](../../cpp/align-cpp.md)です。|
|マネージ コードでは、'_ _imagebase' を使用する関数はサポートされていません|`__ImageBase` 通常のみ使用する低レベル ネイティブ コード DLL を読み込む特別なリンカー記号です。|
|varargs はではサポートされていない、'/clr' コンパイラ オプション|ネイティブ関数を持つマネージ関数を呼び出すことはできません[可変個引数リスト](../../cpp/functions-with-variable-argument-lists-cpp.md)(vararg) 関数が別のスタックのレイアウトの条件を持つためです。 ただし、指定した場合、 **/clr: 純粋な**コンパイラ オプションは、可変個引数が、アセンブリは、マネージ関数のみを含めることができますので、リストはサポートされています。 詳細については、次を参照してください。[純粋なコードと検証可能なコード (C + + CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)です。|
|64 ビット CLR では、_ _ptr32 修飾子で宣言されたデータはサポートされません。|ポインターは、現在のプラットフォームでネイティブ ポインターと同じサイズにする必要があります。 詳細については、次を参照してください。 [_ _ptr32、 \__ptr64](../../cpp/ptr32-ptr64.md)です。|
|32 ビット CLR では、_ _ptr64 修飾子で宣言されたデータはサポートされません。|ポインターは、現在のプラットフォームでネイティブ ポインターと同じサイズにする必要があります。 詳細については、次を参照してください。 [_ _ptr32、 \__ptr64](../../cpp/ptr32-ptr64.md)です。|
|マネージ コードでは、1 つまたは複数の組み込み関数はサポートされていません|メッセージが出力時に、組み込みの名前を使用できません。 ただし、通常このメッセージの原因となる組み込み関数を表す、低レベルのマシン命令です。|
|マネージ コードでは、インラインのネイティブ アセンブリ ('_ _asm') はサポートされていません|[インライン アセンブラー コード](../../assembler/inline/asm.md)は管理できません。 任意のネイティブ コードを含めることができます。|
|_ _Clrcall 非仮想関数のサンクはネイティブとしてコンパイルする必要があります。|以外[_ _clrcall](../../cpp/clrcall.md)仮想関数のサンクは、管理されていないアドレスを使用する必要があります。|
|'_Setjmp' を使用して関数をネイティブとしてコンパイルする必要があります。|CLR は、プログラムの実行を制御できる必要があります。 ただし、 [setjmp](../../cpp/using-setjmp-longjmp.md)関数の保存と復元のレジスタと実行の状態などの低水準の情報によって、通常のプログラム実行をバイパスします。|

## <a name="example"></a>例

次の例では、C4793 を生成します。

```cpp
// C4793.cpp
// compile with: /c /clr /W3
// processor: x86
int asmfunc(void) {   // C4793, compiled as unmanaged, native code
   __asm {
      mov eax, 0
   }
}
```

```Output
warning C4793: 'asmfunc' : function is compiled as native code:
        Inline native assembly ('__asm') is not supported in managed code
```

次の例では、C4793 を生成します。

```cpp
// C4793_b.cpp
// compile with: /c /clr /W3
#include <setjmp.h>
jmp_buf test_buf;

void f() {
   setjmp(test_buf);   // C4793 warning
}
```

```Output
warning C4793: 'f' : function is compiled as native code:
        A function using '_setjmp' must be compiled as native
```
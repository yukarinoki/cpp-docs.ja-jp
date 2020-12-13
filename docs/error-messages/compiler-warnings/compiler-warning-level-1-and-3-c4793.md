---
description: '詳細情報: コンパイラの警告 (レベル1および 3) C4793'
title: コンパイラの警告 (レベル 1 および 3) C4793
ms.date: 11/04/2016
f1_keywords:
- C4793
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
ms.openlocfilehash: 00d8a8c3c0537b1960ee287b2ec5fea25491d87e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336029"
---
# <a name="compiler-warning-level-1-and-3-c4793"></a>コンパイラの警告 (レベル 1 および 3) C4793

> '*function*': 関数はネイティブコードとしてコンパイルされています: '*reason*'

## <a name="remarks"></a>解説

[/Clr](../../build/reference/clr-common-language-runtime-compilation.md)コンパイラオプションが指定されている場合でも、コンパイラは *関数* をマネージコードにコンパイルできません。 代わりに、コンパイラは警告 C4793 と説明の継続メッセージを出力し、 *関数* をネイティブコードにコンパイルします。 継続メッセージには、*関数* をにコンパイルできない理由を説明する *理由* テキストが含まれてい `MSIL` ます。

これは、 **/clr: pure** コンパイラオプションを指定した場合のレベル1の警告です。  **/Clr: pure** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

次の表は、使用可能なすべての継続メッセージの一覧です。

|理由メッセージ|解説|
|--------------------|-------------|
|アラインされたデータ型はマネージコードでサポートされていません|CLR は必要に応じてデータを割り当てることができる必要がありますが、データが [__m128](../../cpp/m128.md) や [アラ](../../cpp/align-cpp.md)インなどの宣言に従って配置されている場合は不可能です。|
|' __ImageBase ' を使用する関数はマネージドコードでサポートされていません|`__ImageBase` は、通常、DLL を読み込むために低レベルのネイティブコードによってのみ使用される特殊なリンカーシンボルです。|
|varargs は '/clr ' コンパイラオプションではサポートされていません|ネイティブ関数は、可変個の [引数リスト](../../cpp/functions-with-variable-argument-lists-cpp.md) (varargs) を持つマネージ関数を呼び出すことはできません。これは、関数のスタックレイアウト要件が異なるためです。 ただし、 **/clr: pure** コンパイラオプションを指定した場合、アセンブリにはマネージ関数だけを含めることができるため、可変個引数リストがサポートされます。 詳細については、「 [純粋なコードと検証可能なコード (C++/cli)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。|
|64ビット CLR は __ptr32 修飾子で宣言されたデータをサポートしていません。|ポインターは、現在のプラットフォームのネイティブポインターと同じサイズである必要があります。 詳細については、「 [__ptr32、 \_ _ptr64](../../cpp/ptr32-ptr64.md)」を参照してください。|
|32ビット CLR は __ptr64 修飾子で宣言されたデータをサポートしていません。|ポインターは、現在のプラットフォームのネイティブポインターと同じサイズである必要があります。 詳細については、「 [__ptr32、 \_ _ptr64](../../cpp/ptr32-ptr64.md)」を参照してください。|
|1つ以上の組み込みがマネージドコードでサポートされていません|組み込みの名前は、メッセージの生成時には使用できません。 ただし、このメッセージの原因となる組み込みは、通常、低レベルのコンピューター命令を表します。|
|インラインのネイティブアセンブリ (' __asm ') はマネージドコードでサポートされていません|[インラインアセンブリコード](../../assembler/inline/asm.md) には、管理できない任意のネイティブコードを含めることができます。|
|非 __clrcall 仮想関数サンクはネイティブとしてコンパイルする必要があります|非[__clrcall](../../cpp/clrcall.md) 仮想関数サンクは、アンマネージアドレスを使用する必要があります。|
|' _Setjmp ' を使用する関数は、ネイティブとしてコンパイルする必要があります|CLR がプログラムの実行を制御できる必要があります。 ただし、 [setjmp](../../cpp/using-setjmp-longjmp.md) 関数は、レジスタや実行状態などの低レベルの情報を保存および復元することによって、通常のプログラムの実行をバイパスします。|

## <a name="example"></a>例

次の例では、C4793 が生成されます。

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

次の例では、C4793 が生成されます。

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

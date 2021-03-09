---
title: 'エラー: グローバルバッファー-オーバーフロー'
description: グローバル変数オーバーフローエラーのソースの例とライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- global-buffer-overflow
helpviewer_keywords:
- global-buffer-overflow error
- AddressSanitizer error global-buffer-overflow
ms.openlocfilehash: cdc637318c523d43684f938df51030ec803a754b
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471242"
---
# <a name="error-global-buffer-overflow"></a>エラー: `global-buffer-overflow`

> Address サニタイザー Error: グローバルバッファーオーバーフロー

コンパイラは、セクションまたはセクション内の任意の変数のメタデータを生成し `.data` `.bss` ます。 これらの変数は、グローバルまたはファイルの静的言語のスコープを持ちます。 これらは、が開始される前にメモリに割り当てら `main()` れます。 C のグローバル変数は、C++ とは大きく異なる方法で処理されます。 この違いは、C をリンクするための複雑なルールが原因です。

C では、グローバル変数はいくつかのソースファイルで宣言できます。また、各定義は異なる型を持つことができます。 コンパイラは、使用可能なすべての定義を一度に見ることはできませんが、リンカーはできます。 C の場合、リンカーは既定で、すべての異なる宣言から最大サイズの変数を選択します。

C++ では、グローバルはコンパイラによって割り当てられます。 定義は1つしか存在できないため、コンパイル時に各定義のサイズがわかっています。

## <a name="example---globals-in-c-with-multiple-type-definitions"></a>例-複数の型定義を持つ ' C ' の globals

```cpp
// file: a.c
int x;
```

```cpp
// file: b.c
char* x;
```

```cpp
// file: c.c
float* x[3];
```

```cpp
// file: example1-main.c
// global-buffer-overflow error

// AddressSanitizer reports a buffer overflow at the first line
// in function main() in all cases, REGARDLESS of the order in 
// which the object files: a.obj, b.obj, and c.obj are linked.
  
double x[5];
 
int main() { 
    int rc = (int) x[5];  // Boom!
    return rc; 
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl a.c b.c c.c example1-main.c /fsanitize=address /Zi
devenv /debugexe example1-main.exe
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/global-overflow-example-1.png" alt-text="例1で、グローバルバッファーオーバーフローエラーを表示しているデバッガーのスクリーンショット。":::

## <a name="example---simple-function-level-static"></a>例-単純な関数レベル static

```cpp
// example2.cpp
// global-buffer-overflow error
#include <string.h>

int 
main(int argc, char **argv) {

    static char XXX[10];
    static char YYY[10];
    static char ZZZ[10];

    memset(XXX, 0, 10); memset(YYY, 0, 10); memset(ZZZ, 0, 10);

    int res = YYY[argc * 10];  // Boom!

    res += XXX[argc] + ZZZ[argc];
    return res;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---simple-function-level-static"></a>生成されたエラー-単純な関数レベル static

:::image type="content" source="media/global-overflow-example-2.png" alt-text="例2で、グローバルバッファーオーバーフローエラーを表示しているデバッガーのスクリーンショット。":::

## <a name="example---all-global-scopes-in-c"></a>例-C++ のすべてのグローバルスコープ

```cpp
// example3.cpp
// global-buffer-overflow error

// Run 4 different ways with the choice of one of these options:
//
// -g : Global
// -c : File static
// -f : Function static
// -l : String literal

#include <string.h>

struct C {
    static int array[10];
};

// normal global
int global[10];

// class static
int C::array[10];

int main(int argc, char **argv) {

    int one = argc - 1;

    switch (argv[1][1]) {
    case 'g': return global[one * 11];     //Boom! simple global
    case 'c': return C::array[one * 11];   //Boom! class static
    case 'f':
        static int array[10];
        memset(array, 0, 10);
        return array[one * 11];            //Boom! function static
    case 'l':
        // literal global ptr created by compiler
        const char *str = "0123456789";
        return str[one * 11];              //Boom! .rdata string literal allocated by compiler
    }
    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe -l
```

### <a name="resulting-error---all-global-scopes-in-c"></a>結果のエラー-C++ のすべてのグローバルスコープ

:::image type="content" source="media/global-overflow-example-3.png" alt-text="例3で、グローバルバッファーオーバーフローエラーを表示しているデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

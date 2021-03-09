---
title: 'エラー: スタック使用-戻り値'
description: ソースの例と、戻りエラーが発生した後にスタックで使用されるライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- stack-use-after-return
helpviewer_keywords:
- stack-use-after-return error
- AddressSanitizer error stack-use-after-return
ms.openlocfilehash: 37d950b0c3b4da880524c0c5825d86d6feec9654
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471217"
---
# <a name="error-stack-use-after-return"></a>エラー: `stack-use-after-return`

> Address サニタイザー Error: 戻り後のスタックメモリの使用

この確認には、追加のコンパイラオプション、 [`/fsanitize-address-use-after-return`](../build/reference/fsanitize.md) 、および環境変数を設定することによってアクティブ化されたコード生成が必要です `ASAN_OPTIONS=detect_stack_use_after_return=1` 。

このチェックにより、アプリケーションの処理速度が大幅に低下する可能性があります。 戻り後の使用をサポートするアルゴリズムの [Clang の概要](https://github.com/google/sanitizers/wiki/AddressSanitizerUseAfterReturn) と、より大きなパフォーマンスコストを考慮してください。

> [!IMPORTANT]
> 追加のコンパイラオプションを使用してオブジェクトファイルを作成した場合 **`/fsanitize-address-use-after-return`** 、コンパイラによって生成されるコードによって、スタックフレームの割り当て方法に関するランタイムの決定が行われます。 環境変数がに設定されていない場合で `ASAN_OPTIONS` `detect_stack_use_after_return` も、コードはそれ自体でを使用する場合よりも遅くなり [`/fsanitize=address`](../build/reference/fsanitize.md) ます。 を使用してフレームの一部に領域を割り当てるスタックフレームのオーバーヘッドが依然として残っているため、速度が低下 `alloca()` します。 返された復帰エラーの処理が完了したら、これらのオブジェクトファイルを削除することをお勧めします。

## <a name="example---simple-c"></a>例-単純 C

```cpp
// example1.cpp
// stack-use-after-return error
char* x;

void foo() {
    char stack_buffer[42];
    x = &stack_buffer[13];
}

int main() {

    foo();
    *x = 42; // Boom!

    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /fsanitize-address-use-after-return /Zi
set ASAN_OPTIONS=detect_stack_use_after_return=1
devenv /debugexe example1.exe
```

### <a name="resulting-error---simple-c"></a>結果のエラー-単純な C

:::image type="content" source="media/stack-use-after-return-example-1.png" alt-text="例1でスタック使用後のエラーを表示するデバッガーのスクリーンショット。":::

## <a name="example---c-and-templates"></a>例-C++ とテンプレート

```cpp
// example2.cpp
// stack-use-after-return error
#include <stdlib.h>

enum ReadOrWrite { Read = 0, Write = 1 };

struct S32 {
    char x[32];
};

template<class T>
T* LeakStack() {
    T t[100];
    static volatile T* x;
    x = &t[0];
    return (T*)x;
}

template<class T>
void StackUseAfterReturn(int Idx, ReadOrWrite w) {
    static T sink;
    T* t = LeakStack<T>();
    if (w)
        t[100 + Idx] = T();
    else
        sink = t[100 + Idx];
}

int main(int argc, char* argv[]) {

    if (argc != 2) return 1;
    int kind = atoi(argv[1]);

    switch (kind) {
    case 1: StackUseAfterReturn<char>(0, Read); break;
    case 2: StackUseAfterReturn<S32>(0, Write); break;
    }
    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example2.cpp /fsanitize=address /fsanitize-address-use-after-return /Zi
set ASAN_OPTIONS=detect_stack_use_after_return=1
devenv /debugexe example2.exe 1
```

### <a name="resulting-error---c-and-templates"></a>結果のエラー-C++ とテンプレート

:::image type="content" source="media/stack-use-after-return-example-2.png" alt-text="例2でスタック使用後のエラーを表示するデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

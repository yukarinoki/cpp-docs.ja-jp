---
title: 'エラー: スタックの使用-適用後'
description: ソースの例と、スコープエラー後のスタック使用のためのライブデバッグのスクリーンショット。
ms.date: 02/05/2021
f1_keywords:
- stack-use-after-scope
helpviewer_keywords:
- stack-use-after-scope error
- AddressSanitizer error stack-use-after-scope
ms.openlocfilehash: 2b6e3ada1cc5b76b371e8059e045735b16d4b334
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470977"
---
# <a name="error-stack-use-after-scope"></a>エラー: `stack-use-after-scope`

> Address サニタイザー Error: スコープ外のスタックメモリの使用

変数の有効期間の構文のスコープ外でスタックアドレスを使用すると、C または C++ で多くの方法で発生する可能性があります。

## <a name="example-1---simple-nested-local"></a>例 1-単純な入れ子になったローカル

```cpp
// example1.cpp
// stack-use-after-scope error
int *gp;

bool b = true;

int main() {
    if (b) {
        int x[5];
        gp = x+1;
    }
    return *gp;  // Boom!
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error---simple-nested-local"></a>生成されたエラー-単純な入れ子になったローカル

:::image type="content" source="media/stack-use-after-scope-example-1.png" alt-text="例1で、スタック使用後のスコープ内エラーを表示するデバッガーのスクリーンショット。":::

## <a name="example-2---lambda-capture"></a>例 2-ラムダキャプチャ

```cpp
// example2.cpp
// stack-use-after-scope error
#include <functional>

int main() {
    std::function<int()> f;
    {
        int x = 0;
        f = [&x]() {
            return x;  // Boom!
        };
    }
    return f();  // Boom!
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---lambda-capture"></a>生成されたエラー-ラムダキャプチャ

:::image type="content" source="media/stack-use-after-scope-example-2.png" alt-text="例2で、スタック使用後のスコープ内エラーを表示するデバッガーのスクリーンショット。":::

## <a name="example-3---destructor-ordering-with-locals"></a>例 3-ローカルでのデストラクターの順序付け

```cpp
// example3.cpp
// stack-use-after-scope error
#include <stdio.h>

struct IntHolder {
    explicit IntHolder(int* val = 0) : val_(val) { }
    ~IntHolder() {
        printf("Value: %d\n", *val_);  // Bom!
    }
    void set(int* val) { val_ = val; }
    int* get() { return val_; }

    int* val_;
};

int main(int argc, char* argv[]) {
    // It's incorrect to use "x" inside the IntHolder destructor,
    // because the lifetime of "x" ends earlier. Per the C++ standard,
    // local lifetimes end in reverse order of declaration.
    IntHolder holder;
    int x = argc;
    holder.set(&x);
    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example3.cpp /fsanitize=address /Zi /O1
devenv /debugexe example3.exe
```

### <a name="resulting-error---destructor-ordering"></a>生成されたエラー-デストラクターの順序

:::image type="content" source="media/stack-use-after-scope-example-3.png" alt-text="例3で、スタック使用後のスコープ内エラーを表示するデバッガーのスクリーンショット。":::

## <a name="example-4---temporaries"></a>例 4-一時要素

```cpp
// example4.cpp
// stack-use-after-scope error
#include <iostream>

struct A {
    A(const int& v) {
        p = &v;
    }
    void print() {
        std::cout << *p;
    }
    const int* p;
};

void explicit_temp() {
    A a(5);     // the temp for 5 is no longer live;
    a.print();
}

void temp_from_conversion() {
    double v = 5;
    A a(v);     // local v is no longer live.
    a.print();
}

void main() {
    explicit_temp();
    temp_from_conversion(); 
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example4.cpp /EHsc /fsanitize=address /Zi
devenv /debugexe example4.exe
```

### <a name="resulting-error---temporaries"></a>結果のエラー-一時要素

:::image type="content" source="media/stack-use-after-scope-example-4.png" alt-text="例4で、スタック使用後のスコープ内エラーを表示するデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

---
title: 'エラー: スタックバッファー-オーバーフロー'
description: スタックバッファーオーバーフローエラーのソースの例とライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- stack-buffer-overflow
helpviewer_keywords:
- stack-buffer-overflow error
- AddressSanitizer error stack-buffer-overflow
ms.openlocfilehash: 52b4dcf2caad04703b9fa407f0546e94528849c4
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471224"
---
# <a name="error-stack-buffer-overflow"></a>エラー: `stack-buffer-overflow`

> アドレスサニタイザーエラー: スタックバッファーオーバーフロー

スタックバッファーオーバーフローは、C または C++ で多くの方法で発生する可能性があります。 このカテゴリのエラーには、単純な再コンパイルでキャッチできるいくつかの例が用意されています。

## <a name="example---stack-buffer-overflow"></a>例-スタックバッファーオーバーフロー

```cpp
// example1.cpp
// stack-buffer-overflow error
#include <string.h>

int main(int argc, char **argv) {
    char x[10];
    memset(x, 0, 10);
    int res = x[argc * 10];  // Boom! Classic stack buffer overflow

    return res;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/stack-buffer-overflow-example-1.png" alt-text="例1でスタックバッファーオーバーフローエラーを表示しているデバッガーのスクリーンショット。":::

## <a name="example---stack-buffer-math"></a>例-スタックバッファーの数値演算

```cpp
// example2.cpp
// stack-buffer-overflow error
#include <string.h>
#include <stdio.h>
#include <stdlib.h>
#include <assert.h>

int main(int argc, char **argv) {
    assert(argc >= 2);
    int idx = atoi(argv[1]);
    char AAA[10], BBB[10], CCC[10];
    memset(AAA, 0, sizeof(AAA));
    memset(BBB, 0, sizeof(BBB));
    memset(CCC, 0, sizeof(CCC));
    int res = 0;
    char *p = AAA + idx;
    printf("AAA: %p\ny: %p\nz: %p\np: %p\n", AAA, BBB, CCC, p);

    return *(short*)(p) + BBB[argc % 2] + CCC[argc % 2];  // Boom! ... when argument is 9
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe 9
```

### <a name="resulting-error---stack-buffer-math"></a>結果のエラー-スタックバッファーの数値演算

:::image type="content" source="media/stack-buffer-overflow-example-2.png" alt-text="例2のスタックバッファーオーバーフローエラーを表示するデバッガーのスクリーンショット。":::

## <a name="example---improper-down-cast-on-stack"></a>例-スタックでの無効なキャスト

```cpp
// example3.cpp
// stack-buffer-overflow error
class Parent {
public:
    int field;
};

class Child : public Parent {
public:
    int extra_field;
};

int main(void) {

    Parent p;
    Child *c = (Child*)&p;  // Boom !
    c->extra_field = 42;

    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe
```

### <a name="resulting-error---improper-down-cast-on-stack"></a>結果のエラー-スタックでの無効なキャスト

:::image type="content" source="media/stack-buffer-overflow-example-3.png" alt-text="例3でスタックバッファーオーバーフローエラーを表示しているデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

---
title: 'エラー: ヒープバッファーオーバーフロー'
description: ヒープ変数オーバーフローエラーのソースの例とライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- heap-buffer-overflow
helpviewer_keywords:
- heap-buffer-overflow error
- AddressSanitizer error heap-buffer-overflow
ms.openlocfilehash: 7eec8d0fa8c7382a5a4ecea9811298aaaba760a2
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470990"
---
# <a name="error-heap-buffer-overflow"></a>エラー: `heap-buffer-overflow`

> Address サニタイザー Error: ヒープバッファーオーバーフロー

この例では、ヒープに割り当てられたオブジェクトの境界の外部でメモリアクセスが発生した場合に発生するエラーを示します。

## <a name="example---classic-heap-buffer-overflow"></a>例-クラシックヒープバッファーオーバーフロー

```cpp
// example1.cpp
// heap-buffer-overflow error
#include <stdlib.h>
#include <string.h>

int main(int argc, char **argv) {

    char *x = (char*)malloc(10 * sizeof(char));
    memset(x, 0, 10);
    int res = x[argc * 10];  // Boom!

    free(x);
    return res;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/heap-buffer-overflow-example-1.png" alt-text="例1でヒープバッファーオーバーフローエラーを表示しているデバッガーのスクリーンショット。":::

## <a name="example---improper-down-cast"></a>例-不適切なダウンキャスト

```cpp
// example2.cpp
// heap-buffer-overflow error
class Parent {
public:
    int field;
};

class Child : public Parent {
public:
    int extra_field;
};

int main(void) {
    Parent *p = new Parent;
    Child *c = (Child*)p;  // Intentional error here!
    c->extra_field = 42;

    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---improper-down-cast"></a>生成されたエラー-ダウンキャストが不適切です

:::image type="content" source="media/heap-buffer-overflow-example-2.png" alt-text="例2で、ヒープバッファーオーバーフローエラーを表示しているデバッガーのスクリーンショット。":::

## <a name="example---strncpy-into-heap"></a>例-ヒープへの strncpy

```cpp
// example3.cpp
// heap-buffer-overflow error
#include <string.h>
#include <stdlib.h>

int main(int argc, char **argv) {

    char *hello = (char*)malloc(6);
    strcpy(hello, "hello");

    char *short_buffer = (char*)malloc(9);
    strncpy(short_buffer, hello, 10);  // Boom!

    return short_buffer[8];
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe
```

### <a name="resulting-error---strncpy-into-heap"></a>生成されたエラー-ヒープへの strncpy

:::image type="content" source="media/heap-buffer-overflow-example-3.png" alt-text="例3で、ヒープバッファーオーバーフローエラーを表示するデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

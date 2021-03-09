---
title: 'エラー: スタックバッファーアンダーフロー'
description: スタックバッファーアンダーフローエラーのソースの例とライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- stack-buffer-underflow
helpviewer_keywords:
- stack-buffer-underflow error
- AddressSanitizer error stack-buffer-underflow
ms.openlocfilehash: 78705933378d7880057d9b7fd13a933f73129fcb
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470980"
---
# <a name="error-stack-buffer-underflow"></a>エラー: `stack-buffer-underflow`

> Address サニタイザー Error: スタックバッファーアンダーフロー

これらのエラーメッセージは、スタック変数の先頭より前の場所へのメモリアクセスを示します。

## <a name="example---local-array-underflow"></a>例-ローカル配列のアンダーフロー

```cpp
// example1.cpp
// stack-buffer-underflow error
#include <stdio.h>

int main() {

    int subscript = -1;
    char buffer[42];
    buffer[subscript] = 42; // Boom!
   
    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/stack-buffer-underflow-example-1.png" alt-text="例1でスタックバッファーアンダーフローエラーを表示しているデバッガーのスクリーンショット。":::

## <a name="example---stack-underflow-on-thread"></a>例-スレッドのスタックアンダーフロー

```cpp
// example2.cpp
// stack-buffer-underflow error
#include <windows.h>

DWORD WINAPI thread_proc(void *) {
    int subscript = -1;
    volatile char stack_buffer[42];
    stack_buffer[subscript] = 42;

    return 0;
}

int main() {
    HANDLE thr = CreateThread(NULL, 0, thread_proc, NULL, 0, NULL);

    if (thr == 0) return 0;

    WaitForSingleObject(thr, INFINITE);

    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error----stack-underflow-on-thread"></a>生成されたエラー-スレッドのスタックアンダーフロー

:::image type="content" source="media/stack-buffer-underflow-example-2.png" alt-text="例2のスタックバッファーアンダーフローエラーを表示するデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

---
title: 'エラー: calloc'
description: Calloc overflow エラーのソースの例とライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- calloc-overflow
helpviewer_keywords:
- calloc-overflow error
- AddressSanitizer error calloc-overflow
ms.openlocfilehash: 63af733061d255924f0b0fbd5f54e4d77359c436
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470992"
---
# <a name="error-calloc-overflow"></a>エラー: `calloc-overflow`

> Address サニタイザー Error: calloc-overflow

CRT 関数は、 [`calloc`](../c-runtime-library/reference/calloc.md) 0 に初期化された要素を使用して、メモリ内に配列を作成します。 引数によって内部エラーが発生し、戻り値として NULL ポインターが生成されることがあります。

## <a name="example"></a>例

```cpp
// example1.cpp
// calloc-overflow error
#include <stdio.h>
#include <stdlib.h>

int number = -1;
int element_size = 1000;

int main() {

    void *p = calloc(number, element_size);      // Boom!

    printf("calloc returned: %zu\n", (size_t)p);

    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/calloc-overflow-example-1.png" alt-text="例1で calloc エラーを表示しているデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

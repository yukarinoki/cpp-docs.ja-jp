---
title: 'エラー: アロケーション-dealloc-不一致'
description: ソースの例と、alloc-dealloc-不一致エラーのライブデバッグスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- alloc-dealloc-mismatch
helpviewer_keywords:
- alloc-dealloc-mismatch error
- AddressSanitizer error alloc-dealloc-mismatch
ms.openlocfilehash: 150809d28631d5d194363e3cb5525163bf7a5e88
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471266"
---
# <a name="error-alloc-dealloc-mismatch"></a>エラー: `alloc-dealloc-mismatch`

> Address サニタイザー Error: 割り当て Api と解放 Api が一致していません

`alloc` / `dealloc` Windows では、AddressSanitizer の不一致機能が既定でオフになっています。 有効にするには、 `set ASAN_OPTIONS=alloc_dealloc_mismatch=1` プログラムを実行する前にを実行します。 この環境変数は `malloc` / `delete` 、、 `new` / `free` 、および `new` / `delete[]` でのエラーを報告するために実行時にチェックされます。

## <a name="example"></a>例

```cpp
// example1.cpp
// alloc-dealloc-mismatch error
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char* argv[]) {

    if (argc != 2) return -1;

    switch (atoi(argv[1])) {

    case 1:
        delete[](new int[10]);
        break;
    case 2:
        delete (new int[10]);      // Boom!
        break;
    default:
        printf("arguments: 1: no error 2: runtime error\n");
        return -1;
    }

    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
set ASAN_OPTIONS=alloc_dealloc_mismatch=1
devenv /debugexe example1.exe 2
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/alloc-dealloc-mismatch-example-1.png" alt-text="例1で、alloc-dealloc-不一致エラーを表示するデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

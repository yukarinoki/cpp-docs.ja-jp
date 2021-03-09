---
title: エラー:-after-有害を使用します
description: 有害エラー後に使用するソースの例とライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- use-after-poison
helpviewer_keywords:
- use-after-poison error
- AddressSanitizer error use-after-poison
ms.openlocfilehash: 0175b79df493dc60c19d78f045ba1829dc0b6b27
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471212"
---
# <a name="error-use-after-poison"></a>エラー: `use-after-poison`

> Address サニタイザー Error: 有害 memory の使用

開発者は、手動で有害なメモリを使用して、デバッグをカスタマイズできます。

## <a name="example"></a>例

```cpp
// example1.cpp
// use-after-poison error
#include <stdlib.h>

extern "C" void __asan_poison_memory_region(void *, size_t);

int main(int argc, char **argv) {
    char *x = new char[16];
    x[10] = 0;
    __asan_poison_memory_region(x, 16);

    int res = x[argc * 10];              // Boom!
 
    delete [] x;
    return res;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/use-after-poison-example-1.png" alt-text="例1で、有害な後エラーを表示するデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

---
title: 'エラー: 割り当てサイズ-大きすぎます'
description: ソースの例と、割り当てサイズのライブデバッグのスクリーンショット-非常に大きなエラーが発生しています。
ms.date: 03/02/2021
f1_keywords:
- allocation-size-too-big
helpviewer_keywords:
- allocation-size-too-big error
- AddressSanitizer error allocation-size-too-big
ms.openlocfilehash: 3320064f52a4d41ca556b9525760997f52e1385b
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471023"
---
# <a name="error-allocation-size-too-big"></a>エラー: `allocation-size-too-big`

> アドレスサニタイザーエラー: 割り当て-サイズ-大きすぎます

この例は、ヒープに対して割り当てが大きすぎる場合に検出されるエラーを示しています。 Llvm コンパイラからのサンプルソース [-rt テストスイート](https://github.com/llvm/llvm-project/tree/main/compiler-rt/test/asan/TestCases)。

## <a name="example"></a>例

```cpp
// example1.cpp
// allocation-size-too-big error
#include <stdio.h>
#include <malloc.h>
#include <memory.h>

int x = 1000;
int y = 1000;

__declspec(noinline) void bad_function() {

  char* buffer = (char*)malloc(x * y * x * y); //Boom!

  memcpy(buffer, buffer + 8, 8); 
}

int main(int argc, char **argv) {
    bad_function();
    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/allocation-size-too-big-example-1.png" alt-text="例1で、割り当てサイズが大きすぎるというエラーが表示されているデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

---
title: 'エラー: strncat が重複しています'
description: Strcat パラメーターオーバーラップエラーのソースの例とライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- strncat-param-overlap
helpviewer_keywords:
- strncat-param-overlap error
- AddressSanitizer error strcat-param-overlap
ms.openlocfilehash: 9ae5b6f602d61f26e1c5d3d9eded35d3f587c53e
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470976"
---
# <a name="error-strncat-param-overlap"></a>エラー: `strncat-param-overlap`

> Address サニタイザー Error: strncat-param

重複するバッファーのメモリを移動するコードは、診断が困難なエラーを発生させる可能性があります。

## <a name="example"></a>例

この例では、AddressSanitizer が、重複するパラメーターによって発生したエラーを CRT 関数にキャッチする方法を示します。

( [Llvm-project/compiler-rt/test/asan/TestCases/strncat-overlap](https://github.com/llvm/llvm-project/blob/62ec4ac90738a5f2d209ed28c822223e58aaaeb7/compiler-rt/test/asan/TestCases/strncat-overlap.cpp)に基づく)。

```cpp
// example1.cpp
// strncat-param-overlap error
#include <string.h>

void bad_function() {
    char buffer[] = "hello\0XXX";
    strncat(buffer, buffer + 1, 3); // BOOM
    return;
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

:::image type="content" source="media/strcat-param-overlap-example-1.png" alt-text="例1で strncat エラーを表示するデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

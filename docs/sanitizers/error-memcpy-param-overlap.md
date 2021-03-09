---
title: 'エラー: memcpy-param-重複'
description: Memcpy パラメーターの重複エラーに関するソースの例とライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- memcpy-param-overlap
helpviewer_keywords:
- memcpy-param-overlap error
- AddressSanitizer error memcpy-param-overlap
ms.openlocfilehash: 1df0310ab2abb326cf895a72afbdffa7c239d9da
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471241"
---
# <a name="error-memcpy-param-overlap"></a>エラー: `memcpy-param-overlap`

> アドレスサニタイザーエラー: memcpy-param-重複

CRT 関数は、 [`memcpy`](../c-runtime-library/reference/memcpy-wmemcpy.md) 重複するメモリをサポートして **いません** 。 CRT は、重複するメモリをサポートするの代替手段を提供します。 `memcpy` [`memmove`](../c-runtime-library/reference/memmove-wmemmove.md)

一般的なエラーとして、と同じ意味を持つとしてを扱うことが `memmove` `memcpy` できます。

## <a name="example"></a>例

```cpp
// example1.cpp
// memcpy-param-overlap error
#include <string.h>

__declspec(noinline) void bad_function() {
    char buffer[] = "hello";

    memcpy(buffer, buffer + 1, 5); // BOOM!
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

:::image type="content" source="media/memcpy-param-overlap-example-1.png" alt-text="例1で、memcpy と param の重複エラーを表示するデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

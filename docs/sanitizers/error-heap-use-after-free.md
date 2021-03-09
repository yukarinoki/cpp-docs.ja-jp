---
title: 'エラー: ヒープを使用します。'
description: ソースの例と、解放されたエラーの後にヒープを使用するためのライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- heap-use-after-free
helpviewer_keywords:
- heap-use-after-free error
- AddressSanitizer error heap-use-after-free
ms.openlocfilehash: 86e64537d40a86b1867e9ba16781f10b6ea9b417
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470988"
---
# <a name="error-heap-use-after-free"></a>エラー: `heap-use-after-free`

> アドレスサニタイザーエラー: 割り当て解除されるメモリの使用

ここでは、ヒープ内のストレージを `malloc` 、、 `realloc` (c)、および `new` (C++) を使用して割り当てることができる3つの例を示し `volatile` ます。

## <a name="example---malloc"></a>例 - `malloc`

```cpp
// example1.cpp
// heap-use-after-free error
#include <stdlib.h>

int main() {
  char *x = (char*)malloc(10 * sizeof(char));
  free(x);

  // ...

  return x[5];   // Boom!
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/heap-use-after-free-example-1.png" alt-text="例1で、ヒープ使用後のエラーを表示するデバッガーのスクリーンショット。":::

## <a name="example---operator-new"></a>例 - `operator new`

```cpp
// example2.cpp
// heap-use-after-free error
#include <windows.h>

int main() {
  char *buffer = new char[42];
  delete [] buffer;

  // ...

  buffer[0] = 42;  // Boom!
  return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---operator-new"></a>結果のエラー-演算子 new

:::image type="content" source="media/heap-use-after-free-example-2.png" alt-text="デバッガーのスクリーンショット (例 2) で、ヒープ使用後のエラーが表示されます。":::

## <a name="example---realloc"></a>例 - `realloc`

```cpp
// example3.cpp
// heap-use-after-free error
#include <malloc.h>

int main() {
  char *buffer = (char*)realloc(0, 42);
  free(buffer);

  // ...

  buffer[0] = 42;  // Boom!
  return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe
```

### <a name="resulting-error---realloc"></a>生成されたエラー-realloc

:::image type="content" source="media/heap-use-after-free-example-3.png" alt-text="デバッガーのスクリーンショット (例 3) で、ヒープ使用後のエラーが表示されます。":::

## <a name="example---volatile"></a>例-volatile

```cpp
// example4.cpp
// heap-use-after-free error
#include <stdlib.h>

int main() {

  volatile char *x = (char*)malloc(sizeof(char));
  free((void*)x);

      //...

  *x = 42;        // Boom!
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example4.cpp /fsanitize=address /Zi
devenv /debugexe example4.exe
```

### <a name="resulting-error---volatile"></a>生成されたエラー-volatile

:::image type="content" source="media/heap-use-after-free-example-4.png" alt-text="例4で、デバッガーがエラーを表示しているスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

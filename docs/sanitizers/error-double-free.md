---
title: 'エラー: ダブルフリー'
description: ソースの例とライブデバッグのスクリーンショット。二重フリーエラーを示しています。
ms.date: 03/02/2021
f1_keywords:
- double-free
helpviewer_keywords:
- double-free error
- AddressSanitizer error double-free
ms.openlocfilehash: 6fb508e581a8c19474311d0406622e6353208433
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471260"
---
# <a name="error-double-free"></a>エラー: `double-free`

> Address サニタイザー Error: 解放されたメモリの解放

C では、を誤って呼び出すことができ `free` ます。 C++ では、を複数回呼び出すことができ `delete` ます。 これらの例では、、、およびでのエラーを示し `delete` `free` `HeapCreate` ます。

## <a name="example-c---double-operator-delete"></a>C++ の例-double `operator delete`

```cpp
// example1.cpp
// double-free error
int main() {

    int *x = new int[42];
    delete [] x;

    // ... some complex body of code

    delete [] x;
    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error---double-operator-delete"></a>結果のエラー-double `operator delete`

:::image type="content" source="media/double-free-example-1.png" alt-text="例1で、ダブルフリーエラーを表示するデバッガーのスクリーンショット。":::

## <a name="example-c---double-free"></a>例: ' C '-double `free`

```cpp
// example2.cpp
// double-free error
#include <stdlib.h>
#include <string.h>

int main(int argc, char** argv) {

    char* x = (char*)malloc(10 * sizeof(char));
    memset(x, 0, 10);
    int res = x[argc];
    free(x);

    // ... some complex body of code

    free(x + argc - 1);  // Boom!
    return res;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---double-free"></a>結果のエラー-double `free`

:::image type="content" source="media/double-free-example-2.png" alt-text="例2で、ダブルフリーエラーを表示するデバッガーのスクリーンショット。":::

## <a name="example---windows-heapcreate-double-heapfree"></a>例-Windows `HeapCreate` double `HeapFree`

```cpp
// example3.cpp
// double-free error
#include <Windows.h>
#include <stdio.h>

int main() {
    void* newHeap = HeapCreate(0, 0, 0);
    void* newAlloc = HeapAlloc(newHeap, 0, 100);

    HeapFree(newHeap, 0, newAlloc);
    HeapFree(newHeap, 0, newAlloc);
    printf("failure\n");
    return 1;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe
```

### <a name="resulting-error---windows-heapcreate-double-heapfree"></a>生成されたエラー-Windows `HeapCreate` double `HeapFree`

:::image type="content" source="media/double-free-example-3.png" alt-text="例3で、ダブルフリーエラーを表示するデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

---
title: 'エラー: ダイナミックスタック-バッファー-オーバーフロー'
description: ソースの例と、alloca エラーのライブデバッグスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- dynamic-stack-buffer-overflow
helpviewer_keywords:
- dynamic-stack-buffer-overflow error
- AddressSanitizer error dynamic-stack-buffer-overflow
ms.openlocfilehash: 4ccf8c9bbab7eb14cac80f0f1d3f9478fc035f8b
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471253"
---
# <a name="error-dynamic-stack-buffer-overflow"></a>エラー: `dynamic-stack-buffer-overflow`

> Address サニタイザー Error: 動的スタック-バッファー-オーバーフロー

この例では、スタックに割り当てられたオブジェクトの境界外へのバッファーアクセスの結果として発生するエラーを示します。

## <a name="example---alloca-overflow-right"></a>例- `alloca` オーバーフロー (右)

```cpp
// example1.cpp
// dynamic-stack-buffer-overflow error
#include <malloc.h>

__declspec(noinline)
void foo(int index, int len) {

    volatile char *str = (volatile char *)_alloca(len);

    //    reinterpret_cast<long>(str) & 31L;

    str[index] = '1'; // Boom !
}

int main(int argc, char **argv) {

    foo(33, 10);
    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/dynamic-stack-buffer-overflow-example-1.png" alt-text="例1で、動的スタックバッファーオーバーフローエラーを表示するデバッガーのスクリーンショット。":::

## <a name="example---alloca-overflow-left"></a>例- `alloca` オーバーフロー (左)

```cpp
// example2.cpp
// dynamic-stack-buffer-overflow error
#include <malloc.h>

__declspec(noinline)
void foo(int index, int len) {

    volatile char *str = (volatile char *)_alloca(len);

    str[index] = '1';  // Boom!
}

int main(int argc, char **argv) {
    foo(-1, 10);
    return 0;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---alloca-overflow-left"></a>結果のエラー- `alloca` オーバーフロー (左)

:::image type="content" source="media/dynamic-stack-buffer-overflow-example-2.png" alt-text="例2で、動的スタックバッファーオーバーフローエラーを表示しているデバッガーのスクリーンショット。":::

## <a name="example---several-calls-to-alloca"></a>例-への複数の呼び出し `alloca`

```cpp
// example3.cpp
// dynamic-stack-buffer-overflow error
#include <stdio.h>
#include <stdlib.h>
#include <malloc.h>

#define SIZE 7
extern void nothing();
int x=13,*aa,*bb,y=0;
int fail = 0;
int tmp;

int main()
{
    int* cc;
    int i;
    int k = 17;
    __try {
        tmp = k;
        aa = (int*)_alloca(SIZE * sizeof(int));
        if (((int)aa) & 0x3)
            fail = 1;
        for (i = 0; i < SIZE; i++) {
            aa[i] = x + 1 + i;
        }
        bb = (int*)_alloca(x * sizeof(int));
        if (((int)bb) & 0x3)
            fail = 1;

        for (i = 0; i < x; i++) {
            bb[i] = 7;
            bb[i] = bb[i] + i;
        }
        {
            int s = 112728283;
            int ar[8];
            for (i = 0; i < 8; i++)
                ar[i] = s * 17 * i;
        }

        cc = (int*)_alloca(x);
        if (((int)cc) & 0x3)
            fail = 1;

        cc[0] = 0;
        cc[1] = 1;
        cc[2] = 2;
        cc[3] = 3;             // <--- Boom!
        for (i = 0; i < x; i++)
            if (bb[i] != (7 + i))
                fail = 1;
        if (tmp != k)
            fail = 1;
        if (fail) {
            printf("fail\n");
            exit(7);
        }
        printf("%d\n", (*cc) / y);
        printf("fail\n");
        exit(7);
    }
    __except (1)
    {
        for (i = 0; i < SIZE; i++)
            if (aa[i] != (x + i + 1))
                fail = 1;
        if (fail) {
            printf("fail\n");
            exit(7);
        }
        printf("pass\n");
        exit(0);
    }
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe
```

### <a name="resulting-error---several-calls-to-alloca"></a>結果のエラー-alloca に対する複数の呼び出し

:::image type="content" source="media/dynamic-stack-buffer-overflow-example-3.png" alt-text="例3で、動的スタックバッファーオーバーフローエラーを表示しているデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

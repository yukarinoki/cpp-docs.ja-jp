---
title: 'エラー: 無効な割り当て-アラインメント'
description: 無効な _aligned_malloc エラーのソースの例とライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- invalid-allocation-alignment
helpviewer_keywords:
- invalid-allocation-alignment error
- AddressSanitizer error invalid-allocation-alignment
ms.openlocfilehash: 99318b068c2908bbe9eee63bef80c5f3f5e37e75
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470982"
---
# <a name="error-invalid-allocation-alignment"></a>エラー: `invalid-allocation-alignment`

> Address サニタイザー Error: 無効な割り当て-アラインメント

[`_aligned_malloc`](../c-runtime-library/reference/aligned-malloc.md)関数のアラインメントを表すには、2の累乗が必要です。 最適化されていないグローバル変数を使用して、一部のアラインメント要因の "外部" 計算をシミュレートします。

## <a name="example"></a>例

```cpp
// example1.cpp
// invalid-allocation-alignment error
#include <Windows.h>

int ExternalAlign = 5;

int main(){

    // this externally calculated alignment of 5 isn't valid.

    void* ptr = _aligned_malloc(8,ExternalAlign); 
    return (ptr == nullptr && errno == EINVAL) ? 0 : -1;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/invalid-allocation-alignment-example-1.png" alt-text="例1で無効な割り当てのアラインメントエラーを表示しているデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

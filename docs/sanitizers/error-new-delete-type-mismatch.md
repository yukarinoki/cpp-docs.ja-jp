---
title: 'エラー: 新規-削除-型が一致しません'
description: 新しい delete 型の不一致エラーのソースの例とライブデバッグのスクリーンショット。
ms.date: 03/02/2021
f1_keywords:
- new-delete-type-mismatch
helpviewer_keywords:
- new-delete-type-mismatch error
- AddressSanitizer error new-delete-type-mismatch
ms.openlocfilehash: 02ea69b16fbb18878fd46544488ac8f3e0d4e3b5
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470987"
---
# <a name="error-new-delete-type-mismatch"></a>エラー: `new-delete-type-mismatch`

> アドレスサニタイザーエラー: 割り当てサイズと異なる割り当て解除サイズ

この例では、、 `~Base` およびではなく、のみ `~Derived` が呼び出されます。 デストラクターがではないため、コンパイラはの呼び出しを生成し `~Base()` `Base` **`virtual`** ます。 を呼び出すと `delete b` 、オブジェクトのデストラクターが既定の定義にバインドされます。 このコードは、空の基本クラス (Windows の場合は1バイト) を削除します。 **`virtual`** デストラクター宣言に見つからないキーワードは、継承を使用する場合の一般的な C++ エラーです。

## <a name="example---virtual-destructor"></a>例-仮想デストラクター

```cpp
// example1.cpp
// new-delete-type-mismatch error
#include <memory>
#include <vector>

struct T {
    T() : v(100) {}
    std::vector<int> v;
};

struct Base {};

struct Derived : public Base {
    T t;
};

int main() {
    Base *b = new Derived;

    delete b;  // Boom! 

    std::unique_ptr<Base> b1 = std::make_unique<Derived>();

    return 0;
}
```

ポリモーフィック基底クラスでは、デストラクターを宣言する必要があり **`virtual`** ます。 クラスに仮想関数がある場合は、仮想デストラクターを持つ必要があります。

この例を修正するには、次のように追加します。

```cpp
struct Base {
  virtual ~Base() = default;
}
```

この例をビルドしてテストするには、Visual Studio 2019 バージョン16.9 以降の [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)で次のコマンドを実行します。

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>結果のエラー

:::image type="content" source="media/new-delete-type-mismatch-example-1.png" alt-text="例1で、新しい-delete 型の不一致エラーを表示するデバッガーのスクリーンショット。":::

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)

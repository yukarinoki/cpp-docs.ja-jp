---
title: AddressSanitizer エラーの例
description: Microsoft C/c + + の AddressSanitizer エラーと例のトップレベルの説明です。
ms.date: 03/01/2021
helpviewer_keywords:
- ASan error examples
- AddressSanitizer error examples
- Address Sanitizer error examples
- Error examples for AddressSanitizer
ms.openlocfilehash: 6f8036139c48b03fb8300f799fbdf05e5006aa4a
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471332"
---
# <a name="addresssanitizer-error-examples"></a>AddressSanitizer エラーの例

このセクションでは、Microsoft C/c + + (MSVC) で AddressSanitizer によってサポートされるエラーのサブセットについて説明します。 この一覧は、完全なエラー一覧ではありません。 これは、AddressSanitizer に表示されるいくつかの種類のエラーを表示することを意図しています。 各記事では、実行中のデバッガーのビルド命令とスクリーンショットを含むサンプルコードを紹介しました。 これらは、MSVC でサポートされている AddressSanitizer 機能をコードで使用する方法を学習するのに役立ちます。 すべてのスクリーンショットは、を使用して生成されました **`devenv.exe /debugexe example.exe`** 。 これらの例の一部は、 [Llvm コンパイラ-rt テストスイート](https://github.com/llvm/llvm-project/tree/main/compiler-rt/test/asan/TestCases)のサンプルコードに基づいています。

## <a name="build-the-error-examples"></a>エラーの例をビルドする

各エラーの例には、コマンドラインビルドのソースコードとコンパイル手順が用意されています。 各例をビルドするには、 [開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)を開きます。 サンプルプロジェクトのフォルダーを作成し、それを現在のディレクトリにします。 次に、などの適切な名前のソースファイルにコード例をコピーし *`example1.cpp`* ます。 ビルドの指示に従って、デバッガーでインストルメント化されたコードを生成して実行します。

## <a name="errors-with-examples"></a>例でのエラー

- [エラー `alloc-dealloc-mismatch`](./error-alloc-dealloc-mismatch.md)

- [エラー `allocation-size-too-big`](./error-allocation-size-too-big.md)

- [エラー `calloc-overflow`](./error-calloc-overflow.md)

- [エラー `double-free`](./error-double-free.md)

- [エラー `dynamic-stack-buffer-overflow`](./error-dynamic-stack-buffer-overflow.md)

- [エラー `global-overflow`](./error-global-buffer-overflow.md)

- [エラー `heap-buffer-overflow`](./error-heap-buffer-overflow.md)

- [エラー `heap-use-after-free`](./error-heap-use-after-free.md)

- [エラー `invalid-allocation-alignment`](./error-invalid-allocation-alignment.md)

- [エラー `memcpy-param-overlap`](./error-memcpy-param-overlap.md)

- [エラー `new-delete-type-mismatch`](./error-new-delete-type-mismatch.md)

- [エラー `stack-buffer-overflow`](./error-stack-buffer-overflow.md)

- [エラー `stack-buffer-underflow`](./error-stack-buffer-underflow.md)

- [エラー `stack-use-after-return`](./error-stack-use-after-return.md)

- [エラー `stack-use-after-scope`](./error-stack-use-after-scope.md)

- [エラー `strncat-param-overlap`](./error-strncat-param-overlap.md)

- [エラー `use-after-poison`](./error-use-after-poison.md)

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)

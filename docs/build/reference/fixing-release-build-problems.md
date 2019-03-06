---
title: リリース ビルドの問題の解決
ms.date: 11/04/2016
helpviewer_keywords:
- release builds, troubleshooting
- debug builds, memory overwrites
- memory, overwrites
- troubleshooting Visual C++, release builds
- troubleshooting release builds
ms.assetid: a0c0818e-4c47-4fe0-a611-50d61a41bd88
ms.openlocfilehash: 3266707f54deb1d0a088e0e9ddd152e922bf67cf
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418543"
---
# <a name="fixing-release-build-problems"></a>リリース ビルドの問題の解決

コードは、デバッグ ビルドをリリース ビルドからの切り替え後のコンパイル エラーを生成する場合は、一部の領域を確認する必要があります。

コンパイラの警告を発生すると、デバッグ ビルド中に受信しなかった最適化 (リリース) のビルド中にあります。

- [ASSERT ステートメントを確認します。](../../build/reference/using-verify-instead-of-assert.md)

- [メモリ上書きのチェックにデバッグ ビルドを使用します。](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)

- [リリース ビルドのデバッグ情報の生成を有効にします。](../../build/reference/how-to-debug-a-release-build.md)

- [メモリ上書きのチェック](../../build/reference/checking-for-memory-overwrites.md)

## <a name="see-also"></a>関連項目

[リリース ビルド](../../build/reference/release-builds.md)<br/>
[リリース ビルド作成時によくある問題](../../build/reference/common-problems-when-creating-a-release-build.md)<br/>
[コードの最適化](../../build/reference/optimizing-your-code.md)

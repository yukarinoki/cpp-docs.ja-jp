---
title: ビルドに関する問題の修正リリース |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- release builds, troubleshooting
- debug builds, memory overwrites
- memory, overwrites
- troubleshooting Visual C++, release builds
- troubleshooting release builds
ms.assetid: a0c0818e-4c47-4fe0-a611-50d61a41bd88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9b304fa6bcc9b0b248719ea44b28e9dae5c76a6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726532"
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
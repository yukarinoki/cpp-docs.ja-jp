---
title: リリース ビルド
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
ms.openlocfilehash: 77e02b424b10b5e9606cc49152c2e21d7eeed9cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667455"
---
# <a name="release-builds"></a>リリース ビルド

リリース ビルドでは、最適化を使用します。 リリース ビルドを作成する最適化を使用すると、コンパイラでは、シンボリック デバッグ情報は生成されません。 トレースとアサートのコードが生成されないことのファクトと共に、シンボリック デバッグ情報の休暇を呼び出すと、実行可能ファイルのサイズが軽減され、高速化ができるためことを意味します。

このセクションでは、デバッグ ビルドからリリース ビルドに変更する理由とタイミングに関する情報を表示します。 デバッグからリリース ビルドに変更するときに発生する問題のいくつか説明します。

- [リリース ビルドを作成します。](../../build/reference/how-to-create-a-release-build.md)

- [リリース ビルド作成時によくある問題](../../build/reference/common-problems-when-creating-a-release-build.md)

- [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)

   - [ASSERT ステートメントを調べる](../../build/reference/using-verify-instead-of-assert.md)

   - [チェックするデバッグ ビルドを使用したメモリ上書き](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)

   - [リリース ビルドをデバッグします。](../../build/reference/how-to-debug-a-release-build.md)

   - [メモリ上書きのチェック](../../build/reference/checking-for-memory-overwrites.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C++ プロジェクトのビルド](../../ide/building-cpp-projects-in-visual-studio.md)<br/>
[C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)
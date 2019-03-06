---
title: リリース ビルド
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
ms.openlocfilehash: 346beace1979871cfd9bf4ee0d487e7f85a26eaa
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426096"
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

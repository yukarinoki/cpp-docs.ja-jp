---
title: C++ リリース ビルド - Visual Studio
ms.date: 12/10/2018
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
ms.openlocfilehash: 46ae5e0f3d545f0e3e004f612314ab416b270fd8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168825"
---
# <a name="release-builds"></a>リリース ビルド

リリース ビルドでは、最適化が使用されます。 最適化を使用してリリース ビルドを作成すると、コンパイラによるシンボリック デバッグ情報の生成は行われません。 シンボリック デバッグ情報の欠如は、TRACE 呼び出しと ASSERT 呼び出し用のコードが生成されないという事実と共に、実行可能ファイルのサイズが縮小され、それによって高速になることを意味します。

## <a name="in-this-section"></a>このセクションの内容

[リリース ビルド作成時によくある問題](common-problems-when-creating-a-release-build.md)<br/>
[リリース ビルドの問題の解決](fixing-release-build-problems.md)<br/>
[ASSERT に代わる VERIFY の使用](using-verify-instead-of-assert.md)<br/>
[デバッグ ビルドを使用したメモリ上書きのチェック](using-the-debug-build-to-check-for-memory-overwrite.md)<br/>
[方法: リリース ビルドをデバッグする](how-to-debug-a-release-build.md)<br/>
[メモリ上書きのチェック](checking-for-memory-overwrites.md)<br/>
[コードの最適化](optimizing-your-code.md)

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](reference/c-cpp-building-reference.md)

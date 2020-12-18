---
description: '詳細情報: リリース ビルド'
title: C++ リリース ビルド - Visual Studio
ms.date: 12/10/2018
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
ms.openlocfilehash: 7168fd50421835edc82d0599b22deb9214e28869
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273788"
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

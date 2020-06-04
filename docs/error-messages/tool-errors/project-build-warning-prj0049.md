---
title: プロジェクト ビルドの警告 PRJ0049
ms.date: 11/04/2016
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
ms.openlocfilehash: e857a50215dc7516c0e2ec45a97638c76f40f43b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191751"
---
# <a name="project-build-warning-prj0049"></a>プロジェクト ビルドの警告 PRJ0049

参照先の '\<Reference > ' には .NET Framework \<MinFrameworkVersion > が必要です。このプロジェクトのターゲットフレームワークでは実行できません

Visual Studio 2008 を使用して作成されたアプリケーションでは、対象とする .NET Framework のバージョンを指定できます。 対象となるバージョンより後の .NET Framework のバージョンに依存するアセンブリまたはプロジェクトへの参照を追加すると、コンパイル時にこの警告が表示されます。

### <a name="to-correct-this-warning"></a>この警告を解決するには

1. 次のいずれかを選択します。

   - プロジェクトの **[プロパティページ]** ダイアログボックスで対象のフレームワークを変更して、参照されているすべてのアセンブリおよびプロジェクトの最小のフレームワークバージョン以上になるようにします。 詳細については、「[参照の追加](../../build/adding-references-in-visual-cpp-projects.md)」を参照してください。

   - 対象のフレームワークよりも後の最小のフレームワークバージョンを持つアセンブリまたはプロジェクトへの参照を削除します。 これらの項目は、プロジェクトの**プロパティページ**で警告アイコンでマークされます。

## <a name="see-also"></a>参照

[プロジェクト ビルド エラーと警告 (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)

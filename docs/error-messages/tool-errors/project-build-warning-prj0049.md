---
description: 詳細については、「プロジェクトビルドの警告 PRJ0049」を参照してください。
title: プロジェクト ビルドの警告 PRJ0049
ms.date: 11/04/2016
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
ms.openlocfilehash: 423b2220cdc80408c71f96c65eb078763291ec3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206358"
---
# <a name="project-build-warning-prj0049"></a>プロジェクト ビルドの警告 PRJ0049

参照先のターゲット ' \<Reference> ' には .NET Framework が必要です。 \<MinFrameworkVersion> このプロジェクトのターゲットフレームワークでは実行できません

Visual Studio 2008 を使用して作成されたアプリケーションでは、対象とする .NET Framework のバージョンを指定できます。 対象となるバージョンより後の .NET Framework のバージョンに依存するアセンブリまたはプロジェクトへの参照を追加すると、コンパイル時にこの警告が表示されます。

### <a name="to-correct-this-warning"></a>この警告を解決するには

1. 次のいずれかを選択します。

   - プロジェクトの [ **プロパティページ** ] ダイアログボックスで対象のフレームワークを変更して、参照されているすべてのアセンブリおよびプロジェクトの最小のフレームワークバージョン以上になるようにします。 詳細については、「 [参照の追加](../../build/adding-references-in-visual-cpp-projects.md)」を参照してください。

   - 対象のフレームワークよりも後の最小のフレームワークバージョンを持つアセンブリまたはプロジェクトへの参照を削除します。 これらの項目は、プロジェクトの **プロパティページ** で警告アイコンでマークされます。

## <a name="see-also"></a>関連項目

[プロジェクトのビルドエラーと警告 (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)

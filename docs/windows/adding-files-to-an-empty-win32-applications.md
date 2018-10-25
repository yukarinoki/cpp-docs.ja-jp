---
title: 空の Win32 アプリケーションへのファイルの追加 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- empty projects [C++], adding files
- projects [C++], adding items
- blank projects
- files [C++], adding to projects
ms.assetid: 070098e8-0396-49fe-a697-3daa2f1be6de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e7ed87390608c05a215caf9c9991c286e5fb0be4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060976"
---
# <a name="adding-files-to-an-empty-win32-applications"></a>空の Win32 アプリケーションへのファイルの追加

### <a name="to-add-your-files-to-an-empty-windows-desktop-application"></a>ファイルを空の Windows デスクトップ アプリケーションに追加するには

1. **ソリューション エクスプローラー**でディレクトリを選びます。

2. ディレクトリ名を右クリックし、ショートカット メニューから **[追加]** をクリックし、次いで **[既存の項目]** をクリックします。

3. **[既存項目の追加] ダイアログ**で、プロジェクトに追加するファイルに移動します。

4. **[OK]** をクリックします。

どちらのソース、ヘッダー、またはリソース ファイルをプロジェクトにファイルを追加するには、右クリックし、**ソリューション**内のノード**ソリューション エクスプ ローラー**と同じ方法でファイルをプロジェクトに追加します。 A **[その他]** フォルダーがプロジェクト内の他のファイルを保持するために作成されます。

> [!NOTE]
> プロジェクトをビルドする前に、完成したアプリケーションに正しく含まれるように、これらのファイル用のビルド オプションを指定する必要があります。 詳しくは、「 [プロパティ ページでプロジェクト設定を指定する](../ide/property-pages-visual-cpp.md) 」と「 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[空の Windows デスクトップ アプリケーションの作成](../windows/creating-an-empty-windows-desktop-application.md)

---
title: プロバイダーのプロジェクトの作成
ms.date: 10/22/2018
helpviewer_keywords:
- ATL projects, creating
- OLE DB providers, projects
- projects [C++], creating
ms.assetid: 076a75de-1d4b-486a-bcf8-9c0f6b049fa2
ms.openlocfilehash: f2ff42ba8a2e908f672db7e96fc9f24f51a1fd9b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211407"
---
# <a name="creating-a-project-for-the-provider"></a>プロバイダーのプロジェクトの作成

## <a name="to-create-a-project-in-which-the-ole-db-provider-will-reside"></a>OLE DB プロバイダーが存在するプロジェクトを作成するには

1. **[ファイル]** メニューの **[新規作成]** をクリックし、 **[プロジェクト]** をクリックします。

   **[新しいプロジェクト]** ダイアログ ボックスが表示されます。

1. **[プロジェクトの種類]** ペインで、[**インストールされている** > **Visual C++**  > **MFC/ATL** ] フォルダーをクリックします。 **[テンプレート]** ペインで、 **[ATL プロジェクト]** をクリックします。

    > [!NOTE]
    > 以前のバージョンの visual Studio では、[**インストールされている** > **テンプレート**] でプロジェクトの種類を見つけて、[  **C++ visual** > **ATL**] > ます。

1. **[名前]** ボックスにプロジェクトの名前を入力し、 **[OK]** をクリックします。

   **ATL プロジェクトウィザード**が表示されます。

1. **ATL プロジェクトウィザード**で、 **[アプリケーションの種類]** の **[ダイナミックリンクライブラリ (DLL)]** を選択します。

1. **[完了]** をクリックします。

## <a name="see-also"></a>参照

[OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)

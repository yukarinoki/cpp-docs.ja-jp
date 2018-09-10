---
title: '方法: C++ プロジェクト (スタンドアロン) の外部のリソース スクリプト ファイルを開く |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resource
dev_langs:
- C++
helpviewer_keywords:
- resources [C++], viewing
- rc files [C++], viewing resources
- .rc files [C++], viewing resources
- resource script files [C++], viewing resources
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6972d76127bccf839c7778e9050e11ec10b6ac2f
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315250"
---
# <a name="how-to-open-a-resource-script-file-outside-of-a-c-project-standalone"></a>方法: C++ プロジェクト (スタンドアロン) の外部のリソース スクリプト ファイルを開く

.rc ファイル内のリソースは、プロジェクトを開かずに表示できます。 ドキュメント ウィンドウで開くことで、.rc ファイルが開きます、[リソース ビュー](../windows/resource-view-window.md)ウィンドウのようなファイルがプロジェクト内で開いているとき)。

> [!NOTE]
> ファイルをスタンドアロンで (プロジェクトの外側で) 開いているときのみ使用できるコマンドがあるため、この違いは重要です。 たとえば、ことができますのみファイルを保存する別の形式で、または別のファイル名としてプロジェクトの外側で、ファイルが開かれたときに (、**名前を付けて保存**コマンドは、プロジェクト内でファイルを開いたときに使用できません)。

### <a name="to-open-an-rc-file-outside-a-project"></a>プロジェクトの外部で .rc ファイルを開くには

1. **ファイル** メニューの 選択**オープン**、 をクリックし、**ファイル**します。

2. **ファイルを開く** ダイアログ ボックスで、表示、ファイルを強調表示 をクリックするリソース スクリプト ファイルを移動**オープン**します。

   > [!NOTE]
   > まず、プロジェクトを開く場合 (**ファイル**、**開く**、**プロジェクト**)、いくつかのコマンドを使用可能にすることはできません。 ファイルを "スタンドアロン" で開くと、プロジェクトを先に読み込むことなくファイルを開くことができます。

開き、テキスト形式でリソース ファイルを表示するには、次を参照してください。[リソース スクリプト (.rc) ファイルを編集](../windows/how-to-open-a-resource-script-file-in-text-format.md)します。

### <a name="to-open-multiple-rc-files-outside-a-project"></a>プロジェクトの外部で複数の .rc ファイルを開くには

1. 2 つのリソース ファイルをスタンドアロンで開きます。 たとえば、開く`Source1.rc`と`Source2.rc`します。

   1. **ファイル** メニューの 選択**オープン**、 をクリックし、**ファイル**します。

   2. **ファイルを開く** ダイアログ ボックスで、最初のリソース スクリプト ファイルを開きたいへ移動 (`Source1.rc`)、ファイルを強調表示し、クリックして**開く**。

   3. 2 番目の .rc ファイルを開くには、前の手順を繰り返します (`Source2.rc`)。

       2 つの .rc ファイルが別個のドキュメント ウィンドウで開きました。

2. 2 つの .rc ファイルを開いているときに、次の手順に従ってウィンドウを並べて表示すると、両方のファイルを同時に見ることができます。

   - **ウィンドウ**] メニューの [選択**水平タブ グループの新しい**または**垂直タブ グループ**します。

       \- または -

   - .Rc ファイルの 1 つを右クリックし **水平タブ グループの新しい**または**垂直タブ グループ**ショートカット メニューから。

> [!NOTE]
> プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイル](../windows/resource-files-visual-studio.md)  
[リソース エディター](../windows/resource-editors.md)
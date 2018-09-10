---
title: '[リソース インクルード] ダイアログ ボックス (C++) |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resourceincludes
dev_langs:
- C++
helpviewer_keywords:
- Resource Includes dialog box [C++]
- rc files [C++], changing storage
- symbol header files [C++], changing
- .rc files [C++], changing storage
- symbol header files [C++], read-only
- symbols [C++], symbol header files
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ea89cdd21f4debfa23716a04630e34e3b9203c1
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313339"
---
# <a name="resource-includes-dialog-box-c"></a>[リソース インクルード] ダイアログ ボックス (C++)

使用することができます、**リソースが含まれています**プロジェクトの .rc ファイル内のすべてのリソースを格納する、環境の通常の作業配置を変更する C++ プロジェクトのダイアログ ボックス[シンボル](../windows/symbols-resource-identifiers.md)Resource.h にします。

開くには、**リソースが含まれています**ダイアログ ボックスで、右クリックして .rc ファイル[リソース ビュー](../windows/resource-view-window.md)を選択し、**リソースが含まれています**ショートカット メニューから。

**シンボル ヘッダー ファイル**  
リソース ファイルのシンボル定義が格納されているヘッダー ファイルの名前を変更することができます。 詳細については、次を参照してください。[シンボル ヘッダー ファイルの名前を変更する](../windows/changing-the-names-of-symbol-header-files.md)します。

**読み取り専用シンボル ディレクティブ**  
編集セッション中に変更してはいけないシンボルが格納されているヘッダー ファイルをインクルードすることができます。 たとえば、いくつかのプロジェクト間で共有されるシンボル ファイルをインクルードできます。 MFC の .h ファイルをインクルードすることもできます。 詳細については、次を参照してください。[共有 (読み取り専用) または計算型シンボル](../windows/including-shared-read-only-or-calculated-symbols.md)します。

**コンパイル時ディレクティブ**  
メイン リソース ファイルのリソースとは個別に作成および編集されたリソース ファイルをインクルードしたり、コンパイル時ディレクティブ (たとえば、条件付きでリソースをインクルードするディレクティブなど) を含めたり、カスタム形式のリソースを含めたりすることができます。 使用することも、**コンパイル時ディレクティブ ボックス**標準 MFC リソース ファイルをインクルードします。 詳細については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)します。

> [!NOTE]
> マークされた .rc ファイルにこれらのテキスト ボックス内のエントリが表示される`TEXTINCLUDE 1`、 `TEXTINCLUDE 2`、および`TEXTINCLUDE 3`それぞれします。 詳細については、次を参照してください。 [TN035: 複数のリソース ファイルを使用すると Visual c ヘッダー ファイル](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)します。

リソース ファイルを使用して変更を行った場合、**リソース ファイルのインクルード**ダイアログ ボックスで、.rc ファイルを閉じてから開き、変更内容を反映する必要があります。 詳細については、次を参照してください。[コンパイル時にリソースを含む](../windows/how-to-include-resources-at-compile-time.md)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[方法: リソースのインクルード ディレクトリを指定する](../windows/how-to-specify-include-directories-for-resources.md)  
[シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)  
[リソース ファイル](../windows/resource-files-visual-studio.md)  
[リソース エディター](../windows/resource-editors.md)
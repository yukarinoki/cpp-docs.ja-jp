---
title: ウィザードでサポートされるその他の言語 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.EastAsianLanguages
dev_langs:
- C++
helpviewer_keywords:
- wizards [C++], language support
- language support for MFC projects
- projects [C++], language support
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75aafd7177c3799c17b75419fd5ab9f54af91d35
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="wizard-support-for-other-languages"></a>ウィザードでサポートされるその他の言語
Visual Studio をインストールするときに、セットアップ アプリケーションは、システムのロケールを検出し、適切な言語のテンプレート、またはそのロケールのテンプレートをインストールします。 たとえば、西ヨーロッパのロケール、セットアップはインストール英語、フランス語、イタリア語、スペイン語、およびドイツ語です。 これらの言語に表示されます、**リソース言語**ボックスの一覧、[アプリケーションの種類](../mfc/reference/application-type-mfc-application-wizard.md)MFC アプリケーション ウィザードのページです。  
  
## <a name="language-templates"></a>言語のテンプレート  
 すべてのテンプレートは、テンプレートは、ANSI エンコーディングおり、すべてのシステムですべてのリソースを編集するために、すべてのシステムにインストールされます。 たとえば、既定では、フランス語のシステム上の日本語リソースを編集することはできません。  
  
 Windows 2000 以降を使用している別の言語で MFC アプリケーションを作成する場合をシステムに、Visual Studio インストーラー メディア (ディスク 1) から適切な言語のテンプレート ディレクトリをコピーする必要があります。  
  
> [!NOTE]
>  作成したプロジェクトを編集するには、選択した言語の適切なロケールに、システム ロケールを設定する必要があります。  
  
 テンプレートは、次の表に記載されている各割り当てる \Microsoft Visual Studio .NET 2003\Vc7\VCWizards\mfcappwiz\templates\ ディレクトリ内のフォルダーです。 テンプレートにアクセスするには、目的の言語、お使いのコンピューター上の \mfcappwiz\templates\ ディレクトリに、適切なフォルダーをコピーします。 フォルダーをコピーしたら、言語に表示されます、**リソース言語**ボックスの一覧、**アプリケーションの種類**MFC アプリケーション ウィザードのページです。  
  
### <a name="language-templates-provided-in-visual-studio-net"></a>Visual Studio .NET で用意されている言語のテンプレート  
  
|言語|テンプレート|  
|--------------|--------------|  
|では |1028|  
|中国語 (簡体字、中国)|2052|  
|英語|1033|  
|フランス語|1036|  
|ドイツ語|1031|  
|イタリア語|1040|  
|日本語|1041|  
|韓国語|1042|  
|スペイン語|3082|  
  
## <a name="format-of-visual-c-wizard-generated-files"></a>Visual C ウィザードで生成されたファイルの形式  
 インストールされている言語バージョンの Visual Studio が、システムのロケールと一致しない場合、Visual C ウィザードで Unicode でプロジェクトが生成されます。 たとえば、日本語バージョンの Visual Studio が日本語以外の言語の地域の設定をあるコンピューターにインストールされているときにし、Visual C ウィザードはプロジェクトを生成 Unicode ファイルで構成されています。 これは、コンピューターを Windows 多言語 (MUI) pack の設定で共通です。  
  
 この動作は、設定するなど、システムのロケールは言語バージョンの Visual Studio と同じシステムによって異なります。 この場合、プロジェクト ファイルは、システム コード ページで ansi 形式で作成されます。  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Visual C++ プロジェクトの作成と管理](../ide/creating-and-managing-visual-cpp-projects.md)
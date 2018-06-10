---
title: ウィザードでサポートされるその他の言語 | Microsoft Docs
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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332443"
---
# <a name="wizard-support-for-other-languages"></a>ウィザードでサポートされるその他の言語
Visual Studio のインストール時には、セットアップ アプリケーションがシステム内にリストされたロケールを検出し、そのロケールに対応する 1 つまたは複数の適切な言語テンプレートをインストールします。 たとえば、西ヨーロッパのロケールの場合は、英語、フランス語、イタリア語、スペイン語、およびドイツ語がインストールされます。 インストールされた言語は、MFC アプリケーション ウィザードの [[アプリケーションの種類]](../mfc/reference/application-type-mfc-application-wizard.md) ページの **[Resource language]\(リソース言語\)** ボックスに表示されます。  
  
## <a name="language-templates"></a>言語テンプレート  
 テンプレートは ANSI エンコードに基づいており、一部のシステムでは編集できないリソースがあります。このため、システムによってはインストールされないテンプレートがあります。 たとえば、既定では、フランス語のシステムでは日本語のリソースを編集できません。  
  
 Windows 2000 以降を使用して他の言語で MFC アプリケーションを作成する場合は、Visual Studio インストーラー メディア (ディスク 1) にある適切な言語のテンプレート ディレクトリをシステムにコピーする必要があります。  
  
> [!NOTE]
>  作成したプロジェクトを編集するには、選択した言語に対応するロケールにシステムのロケールを設定する必要があります。  
  
 次の表に示すように、各テンプレートに対して、\Microsoft Visual Studio .NET 2003\Vc7\VCWizards\mfcappwiz\templates\ ディレクトリのフォルダーが割り当てられています。 使用する言語テンプレートにアクセスするには、該当するフォルダーをコンピューターの \mfcappwiz\templates\ ディレクトリにコピーします。 フォルダーのコピーが完了すると、MFC アプリケーション ウィザードの **[アプリケーションの種類]** ページの **[Resource language]\(リソース言語\)** リストにその言語が表示されます。  
  
### <a name="language-templates-provided-in-visual-studio-net"></a>Visual Studio .NET で指定されている言語テンプレート  
  
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
  
## <a name="format-of-visual-c-wizard-generated-files"></a>Visual C++ ウィザードによって生成されるファイル形式  
 Visual C++ ウィザードでは、インストールされた Visual Studio の言語バージョンがシステムのロケールと異なる場合、プロジェクトが Unicode で生成されます。 たとえば、地域設定が日本語以外のコンピューターに対し、日本語版の Visual Studio をインストールした場合、Visual C++ ウィザードでは、Unicode ファイルから成るプロジェクトが生成されます。 これは、Windows マルチ言語 (MUI) パックでセットアップされたコンピューター全般に言えることです。  
  
 この動作は、システム ロケールが Visual Studio の言語バージョンと同じになるようにセットアップされたシステムとは異なります。 この場合、プロジェクト ファイルはシステム コード ページの ANSI で生成されます。  
  
## <a name="see-also"></a>参照  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Visual C++ プロジェクトの作成と管理](../ide/creating-and-managing-visual-cpp-projects.md)
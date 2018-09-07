---
title: 旧バージョンの Visual C++ からのプロジェクトのアップグレード | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 32-bit code porting
- upgrading Visual C++ applications, 32-bit code
ms.assetid: 18cdacaa-4742-43db-9e4c-2d9e73d8cc84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed8a8ab088f3fbb10b5f477d125dbf3f2a7ac932
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2018
ms.locfileid: "42578209"
---
# <a name="upgrading-projects-from-earlier-versions-of-visual-c"></a>旧バージョンの Visual C++ からのプロジェクトのアップグレード
ほとんどの場合、旧バージョンの Visual Studio で作成されたプロジェクトを開くことができます。 ただし、こうしたプロジェクトは、開くときにアップグレードされます。 アップグレードされたプロジェクトを保存すると、旧バージョンの Visual Studio では開くことができなくなります。  
  
> [!IMPORTANT]
> 既に変換されたプロジェクトを変換しようとすると、再変換によって既存のファイルが削除されるため、その旨を確認するメッセージが表示されます。  
  
アップグレードされたプロジェクトおよびソリューションの多くが、変更なしで正常にビルドできます。 ただし、一部のプロジェクトについては、設定、ソース コード、またはその両方に対する変更が必要になる可能性があります。 まず、次のガイドラインを使用して、設定に関する問題に対処することをお勧めします。その後、プロジェクトをまだビルドできない場合は、コードの問題に対処します。 詳細については、「[Overview of potential upgrade issues](../porting/overview-of-potential-upgrade-issues-visual-cpp.md)」 (アップグレードの潜在的な問題の概要) を参照してください。  
  
1. 既存のプロジェクトおよびソリューション ファイルのコピーを作成します。 必要に応じてファイルのバージョンを比較できるように、現在のバージョンと旧バージョンの Visual Studio を並行してインストールします。  
  
2. 現在のバージョンの Visual Studio で、プロジェクトまたはソリューションのコピーを開いてアップグレードし、保存します。  
  
3. 変換されたプロジェクトごとに、ショートカット メニューを開き、 **[プロパティ]** を選択します。 **[構成プロパティ]** で **[全般]** を選択し、 **[プラットフォーム ツールセット]** で現在のバージョンを選択します (たとえば、Visual Studio 2017 の場合は **v141** を選択)。  
  
4. ソリューションをビルドします。 ビルドに失敗した場合は、設定を変更し、リビルドします。  
  
ストアド プロシージャをデータ ソースで簡単に変更してデバッグできるように、そのソースは個別のデータベース プロジェクトに含まれています。 データ ソースが含まれる C++ プロジェクトをアップグレードすると、個別のデータベース プロジェクトが自動的に作成されます。  
  
対象となる Windows のバージョンを更新する方法については、「[WINVER および _WIN32_WINNT の変更](../porting/modifying-winver-and-win32-winnt.md)」を参照してください。  
  
## <a name="see-also"></a>参照  

[ビルド システムの変更点](../build/build-system-changes.md)  
[Visual Studio 2017 での Visual C++ の新機能](../what-s-new-for-visual-cpp-in-visual-studio.md) 
[Visual C++ の変更履歴 (2003 ～ 2015 年)](../porting/visual-cpp-change-history-2003-2015.md)   
[非標準動作](../cpp/nonstandard-behavior.md)
---
title: ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3e8e5065cebab002e9c48aef560eb9f2feab67e3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33321627"
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル
Visual Studio で ATL プロジェクトを作成する場合、作成するプロジェクト用に選択したオプションに応じて、次のファイルが作成されます。  
  
 これらのファイルはすべて、*Projname* ディレクトリ、およびソリューション エクスプローラーのヘッダー ファイル (.h ファイル) フォルダーまたはソース ファイル (.cpp ファイル) フォルダーにあります。  
  
|ファイル名|説明|  
|---------------|-----------------|  
|*Projname*.h|ATLSample.idl に定義されている項目の C++ インターフェイスの定義および GUID の宣言が含まれた主要なインクルード ファイルです。 これは、コンパイル時に MIDL によって再生成されます。|  
|*Projname*.cpp|プログラムの主要なソース ファイルです。 これには、インプロセス サーバーの DLL のエクスポートの実装と、ローカル サーバーの `WinMain` の実装が含まれています。 サービス用に、追加ですべてのサービス管理機能が実装されています。|  
|Resource.h|リソース ファイルのヘッダー ファイルです。|  
|StdAfx.cpp|StdAfx.h および Atlimpl.cpp ファイルが含まれています。|  
|StdAfx.h|ATL ヘッダー ファイルを含みます。|  
  
## <a name="see-also"></a>参照  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)   
 [MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル](../ide/mfc-program-or-control-source-and-header-files.md)   
 [CLR プロジェクト](../ide/files-created-for-clr-projects.md)
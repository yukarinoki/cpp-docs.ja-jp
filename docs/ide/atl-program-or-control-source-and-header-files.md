---
title: ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル |Microsoft ドキュメント
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
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル
作成するプロジェクトに対して選択したオプションによって、Visual Studio で、ATL プロジェクトを作成するときに、次のファイルが作成されます。  
  
 これらすべてのファイル内にある、 *Projname*ディレクトリ、およびヘッダー ファイル (.h) フォルダーまたはソリューション エクスプ ローラーでフォルダーをソース ファイル (.cpp ファイル) のいずれか。  
  
|ファイル名|説明|  
|---------------|-----------------|  
|*Projname*.h|C++ のインターフェイスの定義となインクルードで定義された項目の GUID の宣言を含むメインのインクルード ファイル。 MIDL によってコンパイル時に再生成されます。|  
|*Projname*.cpp|メイン プログラムのソース ファイルです。 実装と、インプロセス サーバー DLL のエクスポートの実装が含まれている`WinMain`ローカル サーバーです。 サービスの場合はこのさらに、すべてのサービス管理機能を実装します。|  
|Resource.h|リソース ファイルのヘッダー ファイル。|  
|StdAfx.cpp|StdAfx.h と Atlimpl.cpp ファイルが含まれます。|  
|StdAfx.h|ATL ヘッダー ファイルが含まれます。|  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)   
 [MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル](../ide/mfc-program-or-control-source-and-header-files.md)   
 [CLR プロジェクト](../ide/files-created-for-clr-projects.md)
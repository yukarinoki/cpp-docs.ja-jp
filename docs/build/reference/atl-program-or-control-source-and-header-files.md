---
title: ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
ms.openlocfilehash: e315586de57ca65c60c435c436734bcdededed54
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273028"
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル

Visual Studio で ATL プロジェクトを作成する場合、作成するプロジェクト用に選択したオプションに応じて、次のファイルが作成されます。

これらのファイルはすべて、*Projname* ディレクトリ、およびソリューション エクスプローラーのヘッダー ファイル (.h ファイル) フォルダーまたはソース ファイル (.cpp ファイル) フォルダーにあります。

|ファイル名|説明|
|---------------|-----------------|
|<*プロジェクト名*>.h|ATLSample.idl に定義されている項目の C++ インターフェイスの定義および GUID の宣言が含まれた主要なインクルード ファイルです。 これは、コンパイル時に MIDL によって再生成されます。|
|*Projname*.cpp|プログラムの主要なソース ファイルです。 これには、インプロセス サーバーの DLL のエクスポートの実装と、ローカル サーバーの `WinMain` の実装が含まれています。 サービス用に、追加ですべてのサービス管理機能が実装されています。|
|Resource.h|リソース ファイルのヘッダー ファイルです。|
|StdAfx.cpp|StdAfx.h および Atlimpl.cpp ファイルが含まれています。|
|StdAfx.h|ATL ヘッダー ファイルを含みます。|

## <a name="see-also"></a>関連項目

[Visual C++ プロジェクトに対して作成されるファイルの種類](file-types-created-for-visual-cpp-projects.md)<br>
[MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル](mfc-program-or-control-source-and-header-files.md)<br>
[CLR プロジェクト](files-created-for-clr-projects.md)

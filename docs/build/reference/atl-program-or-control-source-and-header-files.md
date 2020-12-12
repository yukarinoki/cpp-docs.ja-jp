---
description: '詳細情報: ATL プログラムまたはコントロールのソースファイルとヘッダーファイル'
title: ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
ms.openlocfilehash: 05407e74931112a1680fb103c20c4a2022185026
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182789"
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル

Visual Studio で ATL プロジェクトを作成する場合、作成するプロジェクト用に選択したオプションに応じて、次のファイルが作成されます。

これらのファイルはすべて、<*プロジェクト名*> ディレクトリ、およびソリューション エクスプローラーのヘッダー ファイル(.h ファイル) フォルダーまたはソース ファイル (.cpp ファイル) フォルダーにあります。

|ファイル名|説明|
|---------------|-----------------|
|*Projname*. h|ATLSample.idl に定義されている項目の C++ インターフェイスの定義および GUID の宣言が含まれた主要なインクルード ファイルです。 これは、コンパイル時に MIDL によって再生成されます。|
|*Projname*.cpp|プログラムの主要なソース ファイルです。 これには、インプロセス サーバーの DLL のエクスポートの実装と、ローカル サーバーの `WinMain` の実装が含まれています。 サービス用に、追加ですべてのサービス管理機能が実装されています。|
|Resource.h|リソース ファイルのヘッダー ファイルです。|
|StdAfx.cpp|StdAfx.h および Atlimpl.cpp ファイルが含まれています。|
|StdAfx.h|ATL ヘッダー ファイルを含みます。|

## <a name="see-also"></a>関連項目

[Visual Studio の C++ プロジェクトに対して作成されるファイルの種類](file-types-created-for-visual-cpp-projects.md)<br>
[MFC プログラムまたはコントロールのソースファイルとヘッダーファイル](mfc-program-or-control-source-and-header-files.md)<br>
[CLR プロジェクト](files-created-for-clr-projects.md)

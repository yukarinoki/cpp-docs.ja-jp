---
title: CLR プロジェクト用に作成されるファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9d66c3f55164a743bc395dc5e9b48f8bcd57654
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="files-created-for-clr-projects"></a>CLR プロジェクト用に作成されるファイル
Visual C のテンプレートを使用して、プロジェクトを作成するときに、使用するテンプレートによって、いくつかのファイルが作成されます。 次の表は、.NET Framework プロジェクトのプロジェクト テンプレートによって作成されるすべてのファイルを一覧表示します。  
  
|ファイル名|ファイルの説明|  
|---------------|----------------------|  
|AssemblyInfo.cpp|プロジェクトのアセンブリ メタデータの変更の情報 (つまり、属性、ファイル、リソース、型、バージョン管理情報、署名情報、およびなど) が含まれるファイル。 詳細については、次を参照してください。[アセンブリ概念](/dotnet/framework/app-domains/assembly-contents)です。|  
|*projname*.asmx|マネージ XML Web サービスの機能をカプセル化するクラスを参照するテキスト ファイルです。|  
|*Projname*.cpp|メインのソース ファイルとエントリは、アプリケーションに自動的に作成する Visual Studio をポイントします。 プロジェクトの .dll ファイルと、プロジェクトの名前空間を識別します。 このファイルには、独自のコードを記述します。|  
|*projname*.vsdisco|XML Web サービスを記述する他のリソースへのリンクを含む XML 展開ファイル。|  
|*Projname*.h|すべての宣言、グローバル シンボルを含むプロジェクトのメインのインクルード ファイルと`#include`他のヘッダー ファイルのディレクティブ。|  
|*projname*.sln|開発環境で 1 つのソリューション、プロジェクトのすべての要素を整理するために使用するソリューション ファイルです。|  
|*Projname*.suo|開発環境で使用されるソリューション オプション ファイルです。|  
|*Projname*.vcxproj|このプロジェクトに固有の情報を格納する開発環境で使用されるプロジェクト ファイルです。|  
|ReadMe.txt|テンプレートによって作成された実際のファイル名を使用して、プロジェクト内の各ファイルを記述するファイルです。|
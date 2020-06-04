---
title: CLR プロジェクト用に作成されるファイル
ms.date: 11/04/2016
helpviewer_keywords:
- Visual Studio C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
ms.openlocfilehash: 45295a3395f19d32dbf29948e1cbd15cd844adb4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169007"
---
# <a name="files-created-for-clr-projects"></a>CLR プロジェクト用に作成されるファイル

Visual C++ テンプレートを使用してプロジェクトを作成するとき、使用するテンプレートに基づき、いくつかのファイルが作成されます。 次の表は、.NET Framework プロジェクトのプロジェクト テンプレートによって作成されるすべてのファイルを一覧にしたものです。

|ファイル名|ファイルの説明|
|---------------|----------------------|
|AssemblyInfo.cpp|プロジェクトのアセンブリ メタデータを変更するための情報 (属性、ファイル、リソース、型、バージョン管理情報、署名情報など) を格納したファイル。 詳細については、「[アセンブリの内容](/dotnet/framework/app-domains/assembly-contents)」を参照してください。|
|*projname*.asmx|XML Web サービスの機能をカプセル化するマネージド クラスを参照するテキスト ファイル。|
|*projname*.cpp|Visual Studio で作成されたアプリケーションのエントリ ポイントであるメイン ソース ファイル。 プロジェクトの .dll ファイルと、プロジェクトの名前空間を識別します。 このファイルには、独自のコードを記述します。|
|*projname*.vsdisco|XML Web サービスを表す他のリソースのリンクを含む XML 展開ファイル。|
|*projname*.h|プロジェクトのメイン インクルード ファイル。このファイルには、すべての宣言、グローバル シンボル、他のヘッダー ファイルについての `#include` ディレクティブが格納されます。|
|*projname*.sln|プロジェクトの全要素を 1 つのソリューションに整理する目的で開発環境内で使用されるソリューション ファイル。|
|*projname*.suo|開発環境内で使用されるソリューション オプション ファイル。|
|*projname*.vcxproj|このプロジェクトに固有の情報を格納する開発環境内で使用されるプロジェクト ファイル。|
|ReadMe.txt|プロジェクト内の各ファイルを、テンプレートで作成された実際のファイル名を使用して説明したファイル。|

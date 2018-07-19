---
title: '移植のガイド: MFC Scribble | Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8ddb517d-89ba-41a1-ab0d-4d2c6d9047e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe0ae0580be4ab062e3ff7ee0cedfb42e201272d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845909"
---
# <a name="porting-guide-mfc-scribble"></a>移植のガイド: MFC Scribble
このトピックは、古いバージョンの Visual Studio で作成された Visual C++ プロジェクトを Visual Studio 2017 にアップグレードする手順を紹介する複数のトピックの 1 つ目です。 これらのトピックでは、例によってアップグレード プロセスを照会し、とてもシンプルなプロジェクトから始めて、少し複雑なものに進みます。 このトピックでは、特定のプロジェクト (MFC Scribble) についてのアップグレード プロセスの作業を行います。 これは、C++ プロジェクトのアップグレード プロセスに関する基本的な紹介として適しています。  
  
 各バージョンの Visual Studio には、古いバージョンの Visual Studio から新しいバージョンへの移動を複雑にする可能性のある、非互換性が持ち込まれることがあります。 必要な変更がコード内にあり、コードを再コンパイルして更新しなければならないことがあり、必要な変更がプロジェクト ファイル内にあることもあります。 以前のバージョンの Visual Studio で作成されたプロジェクトを開くと、Visual Studio によりプロジェクトまたはソリューションを最新バージョンに更新するかどうかが自動的に確認されます。 これらのツールは通常、プロジェクト ファイルのみをアップグレードします。これらは、ソース コードは変更しません。  
  
## <a name="mfc-scribble"></a>MFC Scribble  
 MFC Scribble は、多くの異なるリリースの Visual C++ に含まれている、よく知られているサンプルです。 これは、MFC の基本的な機能の一部を示す、簡単な描画アプリケーションです。 様々なバージョンを利用でき、マネージ コードとネイティブ コードの両方のバージョンがあります。 この例では、Scribble の旧バージョンが Visual Studio 2005 からのネイティブ コードで見つかり、Visual Studio 2017 で開いています。  
  
 アップグレードを試みる前に、Windows デスクトップ ワークロードがインストールされていることを確認します。 Visual Studio インストーラー (vs_installer.exe) を開きます。 インストーラーを開くには、[ファイル | 新しいプロジェクト] を選択し、[Visual Studio インストーラーを開く] が表示されるまで、インストールされたテンプレートを下方にスクロールするという方法があります。 インストーラーを開くと、使用可能なすべてのワークロードが表示されます。 Windows デスクトップ ワークロードに対するボックスが選択されていない場合は、それを選択し、ウィンドウの下部にある [変更] ボタンをクリックします。 


 次に、ソリューション全体と、その内容をすべてバックアップします。 
 
 最後に、特定のアップグレード方式を決定する必要がありました。 長期間アップグレードされていない、さらに複雑なソリューションとプロジェクトについては、一度に 1 つのバージョンの Visual Studio のアップグレードを検討してください。 これにより、Visual Studio のどのバージョンで問題が発生したのか絞り込むことができます。 単純なプロジェクトについては、最新のバージョンの Visual Studio で開こうとすると、ウィザードでプロジェクトを変換することができます。 うまくいかない場合には、適切なバージョンの Visual Studio にアクセスできるなら、一度に 1 つのバージョンをアップグレードすることができます。  
  
 また、ウィザードを使用してプロジェクトをアップグレードする代わりに、コマンドラインで `/Upgrade` オプションを使用して devenv を実行できることに注意してください。 「[/Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe)」を参照してください。 これは、多数のプロジェクトのアップグレード プロセスを自動化するのに役に立ちます。  
  
### <a name="step-1-converting-the-project-file"></a>手順 1. プロジェクト ファイルを変換する  
 Visual Studio 2017 で古いプロジェクト ファイルを開くと、Visual Studio がプロジェクト ファイルの最新バージョンへの変換を提示するので、受け入れます。 次のダイアログ ボックスが表示されました。  
  
 ![プロジェクトとソリューションの変更をレビュー](../porting/media/scribbleprojectupgrade.PNG "ScribbleProjectUpgrade")  
  
 Itanium のターゲットは使用できず、変換されないことを通知するエラーが発生しました。  
  
```Output  
Platform 'Itanium' is missing from this project. All the configurations and their file configuration settings specific to this platform will be ignored. If you want this platform converted, please make sure you have the corresponding platform installed under '%vctargetpath%\platforms\Itanium'.Continue to convert this project without this platform?  
```  
  
 前の Scribble プロジェクトの作成時、Itanium は重要なターゲット プラットフォームでした。 Windows プラットフォームは Itanium をサポートしなくなったので、Itanium プラットフォームをサポートせずに続行するように選択しました。  
  
 Visual Studio で、古いプロジェクト ファイルのすべての問題を一覧表示する、移行レポートが表示されました。  
  
 ![アップグレード レポート](../porting/media/scribblemigrationreport.PNG "ScribbleMigrationReport")  
  
 ここでは、問題がすべて警告であり、Visual Studio がプロジェクト ファイルで適切な変更を行いました。 プロジェクトに関する大きな違いは、ビルド ツールが vcbuild から msbuild に変更されたことです。 この変更は、Visual Studio 2010 で初めて導入されました。 その他の変更点として、プロジェクト ファイル自体にいくつかの要素のシーケンスの再配列が含まれます。 このシンプルなプロジェクトについて、これ以上注意が必要な問題はありません。  
  
### <a name="step-2-getting-it-to-build"></a>手順 2. ビルドできる状態にする  
 ビルド前に、プロジェクト システムがどのコンパイラのバージョンを使用しているのかを知るため、プラットフォーム ツールセットを確認します。 [プロジェクトのプロパティ] ダイアログの **[構成プロパティ]** にある **[全般]** カテゴリで、**[プラットフォーム ツールセット]** プロパティを確認します。 それには、Visual Studio のバージョンとプラットフォームのツールのバージョン番号が含まれ、このケースではツールの Visual Studio 2017 のバージョンは v141 です。 もともと Visual C++ 2010、2012、2013、または 2015 を使用してコンパイルされているプロジェクトを変換する場合、ツールセットは Visual Studio 2017 ツールセットに自動的に更新されません。   
  
  Unicode に切り替えるには、プロジェクトのプロパティを開き、**[構成プロパティ]** で **[全般]** セクションを選択して、**[文字セット]** プロパティを探します。 これを **[マルチ バイト文字セットを使用する]** から **[Unicode 文字セットを使用する]** に変更します。 この変更の影響として、_UNICODE と UNICODE のマクロが定義されて、_MBCS が定義されなくなります。このことは、**[コマンド ライン]** プロパティの **[C/C++]** カテゴリで確認できます。  
  
```Output  
/GS /analyze- /W4 /Zc:wchar_t /Zi /Gm- /Od /Fd".\Debug\vc141.pdb" /Zc:inline /fp:precise /D "_AFXDLL" /D "WIN32" /D "_DEBUG" /D "_WINDOWS" /D "_UNICODE" /D "UNICODE" /errorReport:prompt /WX /Zc:forScope /Gd /Oy- /MDd /Fa".\Debug\" /EHsc /nologo /Fo".\Debug\" /Fp".\Debug\Scribble.pch" /diagnostics:classic 
```  
  
 Scribble プロジェクトは Unicode 文字を使用してコンパイルするように設定されていませんでしたが、既に char の代わりに TCHAR を使用して作成されているので、実際には何も変更する必要がありません。 Unicode 文字セットを使用して、プロジェクトが正常にビルドされます。  
  
 ここで、ソリューションをビルドします。 出力ウィンドウに、コンパイラによって _WINNT32_WINNT が定義されていないことが通知されます。  
  
```Output  
_WIN32_WINNT not defined. Defaulting to _WIN32_WINNT_MAXVER (see WinSDKVer.h)  
```  
  
 これは、エラーではなく警告であり、Visual C++ プロジェクトをアップグレードするときに、ごく一般的に見られます。 これは、アプリケーションが動作する Windows の最も低いバージョンを定義するマクロです。 警告を無視する場合は、現在のバージョンの Windows という意味である、既定値の _WIN32_WINNT_MAXVER をそのまま使用します。 使用可能な値のテーブルについては、「[Using the Windows Headers](https://msdn.microsoft.com/en-us/library/aa383745.aspx)」 (Windows ヘッダーの使用) を参照してください。 たとえば、Vista 以降のすべてのバージョンで動作するよう設定できます。  
  
```  
#define _WIN32_WINNT _WIN32_WINNT_VISTA  
```  
  
 このマクロで指定する Windows のバージョンで利用できない Windows API のパーツをコードが使用している場合には、コンパイラ エラーとして表示されます。 Scribble コードの場合は、エラーはありません。  
  
### <a name="step-3-testing-and-debugging"></a>手順 3. テストおよびデバッグを行う  
 テスト スイートはないため、アプリを起動して、UI から手動で機能をテストしました。 問題は検出されませんでした。  
  
### <a name="step-4-improve-the-code"></a>手順 4. レイアウトを改良する  
 Visual Studio 2017 に移行したので、C++ の新機能を活用するためにいくつかの変更を加えます。 現在のバージョンの C++ コンパイラは、以前のバージョンよりも C++ への適合性が向上しているので、コードの安全性を高めるためにコードを変更し、ほかのコンパイラやオペレーティング システムへの移植性を高めたい場合には、幾らかの改良を加えることを検討してください。  
  
## <a name="next-steps"></a>次の手順  
 Scribble は小規模で単純な Windows デスクトップ アプリケーションであり、変換は難しくありません。 多くの小規模で単純なアプリケーションは、新しいバージョンに簡単に変換できます。  コードの行数が多く、エンジニアリングの最新の標準になっていない可能性がある古いレガシー コードや、複数のプロジェクトとライブラリ、カスタム ビルド アプリを持つ複雑なアプリケーションや、複雑なスクリプトを作成して自動化されていビルドでは、アップグレードにもう少し時間がかかります。 [次の例](../porting/porting-guide-com-spy.md)の COM Spy と呼ばれる ATL/COM アプリケーションに進みます。  
  
## <a name="see-also"></a>参照  
 [移植およびアップグレード: 例とケース スタディ](../porting/porting-and-upgrading-examples-and-case-studies.md)   
 [次の例: COM Spy](../porting/porting-guide-com-spy.md)

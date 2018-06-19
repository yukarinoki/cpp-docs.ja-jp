---
title: 入力 (エントリ ポイント シンボル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /entry
- VC.Project.VCLinkerTool.EntryPointSymbol
dev_langs:
- C++
helpviewer_keywords:
- starting address
- -ENTRY linker option
- /ENTRY linker option
- ENTRY linker option
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74d7e6e05af98bb3d3175d352fb3d5de1b70b12b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375400"
---
# <a name="entry-entry-point-symbol"></a>/ENTRY (エントリ ポイント シンボル)
```  
/ENTRY:function  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *function*  
 ユーザーが定義した開始を指定する関数は、.exe ファイルまたは DLL のアドレスします。  
  
## <a name="remarks"></a>コメント  
 /ENTRY オプションは、.exe ファイルまたは DLL の開始アドレスとしてエントリ ポイント関数を指定します。  
  
 使用する関数を定義する必要があります、`__stdcall`呼び出し規約です。 パラメーターと戻り値かどうか、プログラムは、コンソール アプリケーション、windows アプリケーションまたは DLL に依存します。 エントリ ポイントを設定して、C ランタイム ライブラリは正しく初期化されており、静的オブジェクト用の C++ コンス トラクターが実行されるようにリンカーを使用することをお勧めします。  
  
 既定では、開始アドレスは、C ランタイム ライブラリの関数名がします。 リンカーは、プログラムの属性に従って次の表に示すように、ように選択します。  
  
|関数名|既定値|  
|-------------------|-----------------|  
|**mainCRTStartup** (または**wmainCRTStartup**)|/SUBSYSTEM:CONSOLE; を使用するアプリケーション呼び出し`main`(または`wmain`)|  
|**WinMainCRTStartup** (または**wWinMainCRTStartup**)|/SUBSYSTEM を使用するアプリケーションを:**WINDOWS**; 呼び出し`WinMain`(または`wWinMain`)、使用が定義されている必要があります `__stdcall`|  
|**_DllMainCRTStartup**|DLL です。呼び出し`DllMain`、存在する場合を定義する必要があるには `__stdcall`|  
  
 場合、 [/DLL](../../build/reference/dll-build-a-dll.md)または[/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)をリンカーがかどうかに応じて、サブシステムとエントリ ポイントを選択して、オプションが指定されていない`main`または`WinMain`が定義されています。  
  
 関数は、 `main`、 `WinMain`、および`DllMain`ユーザー定義のエントリ ポイントの 3 つの形式です。  
  
 /ENTRY に指定された関数のシグネチャがありますをマネージ イメージを作成する場合 (LPVOID *var1*、DWORD *var2*、LPVOID *var3*)。  
  
 独自に定義する方法について`DllMain`エントリ ポイントを参照してください[Dll および Visual C ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**詳細**プロパティ ページ。  
  
4.  変更、**エントリ ポイント**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)
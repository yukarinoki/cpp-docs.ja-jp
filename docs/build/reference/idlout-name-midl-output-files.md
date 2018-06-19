---
title: -IDLOUT (MIDL の出力ファイルの名前を付ける) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
dev_langs:
- C++
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7eeb7af3d19a57b6948f867df87b8d04d0397b0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376063"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT (MIDL 出力ファイルの指定)
```  
/IDLOUT:[path\]filename  
```  
  
## <a name="parameters"></a>パラメーター  
 *path*  
 絶対または相対パスを指定します。 .Idl ファイルの場所だけに影響するパスを指定すると、その他のすべてのファイルは、プロジェクト ディレクトリに配置されます。  
  
 *ファイル名*  
 MIDL コンパイラによって作成された .idl ファイルの名前を指定します。 ファイル拡張子は付加されません。指定*filename*.idl .idl 拡張する場合。  
  
## <a name="remarks"></a>コメント  
 /IDLOUT オプションは、.idl ファイルの拡張機能と名前を指定します。  
  
 MIDL コンパイラを持つプロジェクトをリンクするときに、Visual C リンカーによって呼び出されます。、[モジュール](../../windows/module-cpp.md)属性。  
  
 /IDLOUT には、MIDL コンパイラに関連付けられているその他の出力ファイルのファイル名も指定します。  
  
-   *filename*.tlb  
  
-   *filename*_p.c  
  
-   *filename*_i.c  
  
-   *filename*.h  
  
 *filename* /IDLOUT に渡すパラメーターです。 場合[/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)を指定すると、.tlb ファイルは/TLBOUT からその名前を取得*filename*です。  
  
 /IDLOUT も/TLBOUT を指定する場合、リンカーは、vc70.tlb、vc70.idl、vc70_p.c、vc70_i.c、および vc70.h に作成されます。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**埋め込み IDL**プロパティ ページ。  
  
4.  変更、 **IDL ベース ファイル名のマージ**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [/IGNOREIDL (しない属性の処理を MIDL に挿入)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/MIDL (MIDL コマンド ライン オプションの指定)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [属性付きプログラムの作成](../../windows/building-an-attributed-program.md)
---
title: -SUBSYSTEM (サブシステムの指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
dev_langs:
- C++
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70d6f047cf18b8b768d40533e2acc6cb2f649327
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM (サブシステムの指定)
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|  
            POSIX|WINDOWS)  
            [,major[.minor]]  
```  
  
 BOOT_APPLICATION  
 Windows のブート環境で実行するアプリケーションです。 ブート アプリケーションの詳細については、次を参照してください。 [About BCD](http://msdn.microsoft.com/library/windows/desktop/aa362639)です。  
  
 CONSOLE  
 Win32 文字モード アプリケーションに対して使用します。 オペレーティング システムには、コンソール アプリケーションのコンソールが用意されています。 ネイティブ コードに `main` または `wmain` が定義されている場合、マネージ コードに `int main(array<String ^> ^)` が定義されている場合、または `/clr:safe` を使用してアプリケーションを完全にビルドする場合、CONSOLE が既定の設定になります。  
  
 拡張可能なファームウェア インターフェイス  
 EFI_* サブシステムです。 詳細については、EFI の仕様を参照してください。 たとえば、Intel の Web サイトなどを参照してください。 最小および既定のバージョンは 1.0 です。  
  
 NATIVE  
 Windows NT 用のカーネル モード ドライバーです。 このオプションは、通常、Windows システム コンポーネントのために予約されています。 場合[/DRIVER:WDM](../../build/reference/driver-windows-nt-kernel-mode-driver.md)を指定すると、既定では、ネイティブです。  
  
 POSIX  
 Windows NT 上の POSIX サブシステムで実行するアプリケーションです。  
  
 WINDOWS  
 アプリケーションにはコンソールは不要です。このシステムにはユーザーとの対話用のウィンドウが作成されるからです。 ネイティブ コードに `WinMain` または `wWinMain` が定義されている場合、あるいはマネージ コードに `WinMain(HISTANCE *, HINSTANCE *, char *, int)` または `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` が定義されている場合、WINDOWS が既定の設定になります。  
  
 `Major` および `minor` (省略可能)  
 サブシステムに最低限必要なバージョンを指定します。 引数には、0 ～ 65535 の範囲の 10 進数を指定します。 詳細については、「解説」を参照してください。 バージョン番号に上限はありません。  
  
## <a name="remarks"></a>コメント  
 /SUBSYSTEM オプションは、実行可能ファイルの環境を指定します。  
  
 サブシステムの選択によって、リンカーが選択するエントリ ポイント シンボル (またはエントリ ポイント関数) が決まります。  
  
 サブシステムに必要な最小限の既定の `major` および `minor` のバージョン番号は以下のとおりです。  
  
|サブシステム|最小要件|既定値|  
|---------------|-------------|-------------|  
|BOOT_APPLICATION|1|1|  
|CONSOLE|5.01 (x86) 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|6.00 (x86、[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|WINDOWS|5.01 (x86) 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|6.00 (x86、[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|NATIVE (DRIVER:WDM を使用する場合)|1.00 (x86) 1.10 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]、ARM)|1.00 (x86) 1.10 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]、ARM)|  
|NATIVE (/DRIVER:WDM を使用しない場合)|(x86) 4.00 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|(x86) 4.00 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|POSIX|1|19.90|  
|EFI_APPLICATION、EFI_BOOT_SERVICE_DRIVER、EFI_ROM、EFI_RUNTIME_DRIVER|1|1|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  [リンカー] フォルダーを選択します。  
  
3.  選択、**システム**プロパティ ページ。  
  
4.  `SubSystem` プロパティを変更します。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)
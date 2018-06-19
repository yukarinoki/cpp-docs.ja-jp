---
title: -INTEGRITYCHECK (シグネチャ確認が必要) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 997e3f5bb79ee3cbfa95c5762b0d3e998c56f362
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374246"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (シグネチャ確認が必要)
読み込み時にバイナリ イメージのデジタル署名を確認する必要があることを指定します。  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 既定では、 **/INTEGRITYCHECK**は無効になっています。  
  
 **/INTEGRITYCHECK**オプション セットに、DLL ファイルまたは実行可能ファイルの PE ヘッダーに — メモリ マネージャーは Windows でイメージを読み込むために、デジタル署名の確認に使用するフラグ。 このオプションは、特定の Windows 機能によって読み込まれるカーネル モード コードを実装する、32 ビットと 64 ビットの両方の DLL に対して設定する必要があり、Windows Vista、[!INCLUDE[win7](../../build/includes/win7_md.md)]、[!INCLUDE[win8](../../build/reference/includes/win8_md.md)]、[!INCLUDE[winsvr08](../../build/reference/includes/winsvr08_md.md)]、[!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)] のすべてのデバイス ドライバーに推奨されます。 Windows Vista 以前の Windows は、このフラグを無視します。 詳細については、次を参照してください。[強制整合性署名のポータブル実行可能 (PE) ファイル](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)です。  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**コマンドライン**プロパティ ページ。  
  
5.  **追加オプション**、入力`/INTEGRITYCHECK`または`/INTEGRITYCHECK:NO`です。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [強制整合性署名のポータブル実行可能 (PE) ファイル](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [カーネル モード コード署名のチュートリアル](http://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [Windows 7 および Windows Server 2008 で AppInit Dll](http://msdn.microsoft.com/windows/hardware/gg463040.aspx)
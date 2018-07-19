---
title: -DEBUGTYPE (デバッグ情報オプション) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /debugtype
dev_langs:
- C++
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66868f7648d20b890f3c1e8c40802d77e3af4544
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375371"
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE (デバッグ情報オプション)
/DEBUGTYPE オプションは、/DEBUG オプションによって生成されるデバッグ情報の種類を指定します。  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## <a name="arguments"></a>引数  
 CV  
 シンボル、行番号、その他のオブジェクトのコンパイル情報のデバッグ情報を PDB ファイルに出力するようにリンカーに指示します。 既定では、このオプションが有効になっているときに **/debug**が指定されていると **/DEBUGTYPE**が指定されていません。  
  
 PDATA  
 .pdata エントリと .xdata エントリを PDB ファイル内のデバッグ ストリーム情報に追加するようにリンカーに指示します。 既定では、このオプションが有効になっているときに両方、 **/debug**と **/DRIVER**オプションを指定します。 場合 **/DEBUGTYPE:PDATA**が指定されて、単独でリンカーが自動的にデバッグ シンボルを PDB ファイルを追加します。 場合 **/DEBUGTYPE:PDATA、フィックス アップ**を指定すると、リンカーはデバッグ シンボルを PDB ファイルに含まれません。  
  
 FIXUP  
 再配置テーブル エントリを PDB ファイル内のデバッグ ストリーム情報に追加するようにリンカーに指示します。 既定では、このオプションが有効になっているときに両方、 **/debug**と **/profile**オプションを指定します。 場合 **/DEBUGTYPE:FIXUP**または **/DEBUGTYPE:FIXUP、PDATA**を指定すると、リンカーはデバッグ シンボルを PDB ファイルに含まれません。  
  
 引数を **/DEBUGTYPE**コンマで区切って任意の順序で組み合わせることができます。 **/DEBUGTYPE**オプションとその引数は、大文字小文字が区別されません。  
  
## <a name="remarks"></a>コメント  
 使用して、 **/DEBUGTYPE**デバッグ ストリームに従った再配置テーブル データまたは .pdata および .xdata ヘッダー情報を含めることを指定するにはオプションです。 これにより、リンカーは、カーネルモード コードで中断するときにカーネル デバッガーに表示されるユーザーモード コードに関する情報を含めます。 ときにデバッグ シンボルを使用できるようにする**フィックス アップ**が指定すると、含める、 **CV**引数。  
  
 アプリケーションで一般的には、ユーザー モードでコードをデバッグする、 **/DEBUGTYPE**オプションは必要ありません。 既定では、デバッグを指定するコンパイラ スイッチの出力 ([/Z7、/Zi、/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)) については、必要に応じて、Visual Studio でデバッガーのすべてを出力します。 使用して **/DEBUGTYPE:PDATA**または **/DEBUGTYPE:CV, PDATA、FIXUP**デバイス ドライバーの構成アプリなど、ユーザー モードおよびカーネル モードのコンポーネントを組み合わせてするコードをデバッグします。 カーネル モード デバッガーの詳細については、次を参照してください[Windows 用デバッグ ツール (WinDbg、KD、CDB、NTSD)。](http://go.microsoft.com/fwlink/p?LinkID=285651)  
  
## <a name="see-also"></a>関連項目  
 [/DEBUG (デバッグ情報の生成)](../../build/reference/debug-generate-debug-info.md)   
 [/DRIVER (Windows NT カーネル モード ドライバー)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [/PROFILE (パフォーマンス ツール プロファイラー)](../../build/reference/profile-performance-tools-profiler.md)   
 [(WinDbg、KD、CDB、NTSD) の Windows 用デバッグ ツール](http://go.microsoft.com/fwlink/p?LinkID=285651)
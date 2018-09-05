---
title: -DEBUGTYPE (デバッグ情報オプション) |Microsoft Docs
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
ms.openlocfilehash: ce4db4403f034a5795237393a8f1465fdf31982b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681082"
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE (デバッグ情報オプション)
/DEBUGTYPE オプションは、/DEBUG オプションによって生成されるデバッグ情報の種類を指定します。  
  
```  
/DEBUGTYPE:[CV | PDATA | FIXUP]  
```  
  
## <a name="arguments"></a>引数  
 CV  
 シンボル、行番号、その他のオブジェクトのコンパイル情報のデバッグ情報を PDB ファイルに出力するようにリンカーに指示します。 既定では、このオプションが有効になっているときに **/debug**が指定されて、 **/DEBUGTYPE**が指定されていません。  
  
 PDATA  
 .pdata エントリと .xdata エントリを PDB ファイル内のデバッグ ストリーム情報に追加するようにリンカーに指示します。 既定では、このオプションが有効になっているときに両方、 **/debug**と **/DRIVER**オプションを指定します。 場合 **/DEBUGTYPE:PDATA**リンカーが自動的にデバッグ シンボルを PDB ファイルを含む、自体によって指定されます。 場合 **/DEBUGTYPE:PDATA、フィックス アップ**指定すると、リンカーはデバッグ シンボルを PDB ファイルに含まれません。  
  
 FIXUP  
 再配置テーブル エントリを PDB ファイル内のデバッグ ストリーム情報に追加するようにリンカーに指示します。 既定では、このオプションが有効になっているときに両方、 **/debug**と **/profile**オプションを指定します。 場合 **/DEBUGTYPE:FIXUP**または **/DEBUGTYPE:FIXUP、PDATA**指定すると、リンカーはデバッグ シンボルを PDB ファイルに含まれません。  
  
 引数を **/DEBUGTYPE**をコンマで区切ることによって任意の順序で組み合わせることができます。 **/DEBUGTYPE**オプションとその引数は大文字小文字が区別されません。  
  
## <a name="remarks"></a>Remarks  
 使用して、 **/DEBUGTYPE**デバッグ ストリームで再配置テーブル データまたは .pdata および .xdata ヘッダー情報を含めることを指定するオプション。 これにより、リンカーは、カーネルモード コードで中断するときにカーネル デバッガーに表示されるユーザーモード コードに関する情報を含めます。 ときにデバッグ シンボルを使用できるようにする**FIXUP**が指定すると、含める、 **CV**引数。  
  
 アプリケーションの一般的なものは、ユーザー モードでコードをデバッグする、 **/DEBUGTYPE**オプションは必要ありません。 既定では、デバッグを指定するコンパイラ スイッチが出力 ([/Z7、/Zi、/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)) すべてについては、必要な Visual Studio でデバッガーの出力します。 使用 **/DEBUGTYPE:PDATA**または **/DEBUGTYPE:CV, PDATA、FIXUP**デバイス ドライバーの構成アプリなど、ユーザー モードおよびカーネル モードのコンポーネントを組み合わせてするコードをデバッグします。 カーネル モード デバッガーの詳細については、次を参照してください[デバッグ ツールの Windows (WinDbg、KD、CDB、NTSD)。](/windows-hardware/drivers/debugger/index)  
  
## <a name="see-also"></a>関連項目  
 [/DEBUG (Generate Debug Info)](../../build/reference/debug-generate-debug-info.md)   
 [/DRIVER (Windows NT カーネル モード ドライバー)](../../build/reference/driver-windows-nt-kernel-mode-driver.md)   
 [/PROFILE (パフォーマンス ツール Profiler)](../../build/reference/profile-performance-tools-profiler.md)   
 [(WinDbg、KD、CDB、NTSD)、Windows 用デバッグ ツール](/windows-hardware/drivers/debugger/index)
---
description: 詳細情報:/DEBUGTYPE (デバッグ情報オプション)
title: /DEBUGTYPE (デバッグ情報オプション)
ms.date: 11/04/2016
f1_keywords:
- /debugtype
helpviewer_keywords:
- /DEBUGTYPE linker option
- DEBUGTYPE linker option
- -DEBUGTYPE linker option
ms.assetid: 1ddcb718-7fec-4f92-a319-3f70f04fe742
ms.openlocfilehash: 858d5ed8eb449931229700a10b755dd61ef371cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201730"
---
# <a name="debugtype-debug-info-options"></a>/DEBUGTYPE (デバッグ情報オプション)

/DEBUGTYPE オプションは、/DEBUG オプションによって生成されるデバッグ情報の種類を指定します。

```
/DEBUGTYPE:[CV | PDATA | FIXUP]
```

## <a name="arguments"></a>引数

**CV**<br/>
シンボル、行番号、その他のオブジェクトのコンパイル情報のデバッグ情報を PDB ファイルに出力するようにリンカーに指示します。 既定では、このオプションは、 **/debug** が指定されていて、 **/DEBUGTYPE** が指定されていない場合に有効になります。

**PDATA**<br/>
.pdata エントリと .xdata エントリを PDB ファイル内のデバッグ ストリーム情報に追加するようにリンカーに指示します。 既定では、このオプションは、 **/debug** オプションと **/DRIVER** オプションの両方が指定されている場合に有効になります。 **/DEBUGTYPE: PDATA** がそれ自体によって指定されている場合、リンカーは自動的に PDB ファイルにシンボルをデバッグします。 **/DEBUGTYPE: PDATA、FIXUP** が指定されている場合、リンカーにはデバッグシンボルが PDB ファイルに含まれません。

**FIXUP**<br/>
再配置テーブル エントリを PDB ファイル内のデバッグ ストリーム情報に追加するようにリンカーに指示します。 既定では、このオプションは、 **/debug** オプションと **/profile** オプションの両方が指定されている場合に有効になります。 **/DEBUGTYPE: fixup** または **/DEBUGTYPE: fixup** が指定されている場合、リンカーにはデバッグシンボルが PDB ファイルに含まれません。

**/DEBUGTYPE** への引数は、コンマで区切ることで、任意の順序で組み合わせることができます。 **/DEBUGTYPE** オプションとその引数では、大文字と小文字が区別されません。

## <a name="remarks"></a>解説

**/DEBUGTYPE** オプションを使用して、デバッグストリームで再配置テーブルデータまたは pdata と .xdata ヘッダー情報を含めるように指定します。 これにより、リンカーは、カーネルモード コードで中断するときにカーネル デバッガーに表示されるユーザーモード コードに関する情報を含めます。 **FIXUP** を指定したときにデバッグシンボルを使用できるようにするには、 **CV** 引数を含めます。

アプリケーションの一般的なユーザーモードでコードをデバッグするには、 **/DEBUGTYPE** オプションは必要ありません。 既定では、デバッグ出力を指定するコンパイラスイッチ ([/Z7、/zi、/zi](z7-zi-zi-debug-information-format.md)) は、Visual Studio デバッガーで必要なすべての情報を出力します。 **/DEBUGTYPE: pdata** または **/DEBUGTYPE: CV、pdata、FIXUP** を使用して、デバイスドライバーの構成アプリなど、ユーザーモードとカーネルモードのコンポーネントを組み合わせたコードをデバッグします。 カーネルモードのデバッガーの詳細については、「 [Windows 用デバッグツール (WinDbg、KD、CDB、NTSD)](/windows-hardware/drivers/debugger/index) 」を参照してください。

## <a name="see-also"></a>関連項目

[/DEBUG (デバッグ情報の生成)](debug-generate-debug-info.md)<br/>
[/DRIVER (Windows NT カーネルモードドライバー)](driver-windows-nt-kernel-mode-driver.md)<br/>
[/PROFILE (パフォーマンスツールプロファイラー)](profile-performance-tools-profiler.md)<br/>
[Debugging Tools for Windows (WinDbg、KD、CDB、NTSD)](/windows-hardware/drivers/debugger/index)

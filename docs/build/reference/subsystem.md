---
title: /SUBSYSTEM
ms.date: 11/04/2016
f1_keywords:
- /subsystem_editbin
helpviewer_keywords:
- /SUBSYSTEM editbin option
- -SUBSYSTEM editbin option
- SUBSYSTEM editbin option
ms.assetid: 515e4cdf-3cc4-4659-8764-1f2757b49215
ms.openlocfilehash: 708bfcce3e6d6616116bcc08441f374b46914c82
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438864"
---
# <a name="subsystem"></a>/SUBSYSTEM

実行可能イメージに必要な実行環境を指定します。

```
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|
        EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|
        NATIVE|POSIX|WINDOWS|WINDOWSCE}[,major[.minor]]
```

## <a name="remarks"></a>コメント

このオプションは、イメージを編集して、実行のためにオペレーティング システムから呼び出すサブシステムを指定します。

以下のいずれかのサブシステムを指定できます。

**BOOT_APPLICATION**<br/>
Windows のブート環境で実行するアプリケーションです。 ブートアプリケーションの詳細については、「 [BCD WMI プロバイダーについ](/previous-versions/windows/desktop/bcd/about-bcd)て」を参照してください。

**コンソール**<br/>
Windows キャラクター モード アプリケーション。 オペレーティング システムには、コンソール アプリケーションのコンソールが用意されています。

**EFI_APPLICATION**<br/>
**EFI_BOOT_SERVICE_DRIVER**<br/>
**EFI_ROM**<br/>
**EFI_RUNTIME_DRIVER**<br/>
拡張可能なファームウェア インターフェイス (EFI) イメージ

EFI サブシステムのオプションは、拡張可能なファームウェア インターフェイスの環境で実行できる実行可能イメージを設定します。 この環境は通常、ハードウェアと共に提供され、オペレーティング システムが読み込まれる前に実行されます。 EFI のイメージの種類による主な相違点は、イメージが読み込まれるメモリ位置、およびイメージへの呼び出しが返されるときに実行される処理です。 EFI_APPLICATION イメージは、制御が返されるとアンロードされます。 EFI_BOOT_SERVICE_DRIVER または EFI_RUNTIME_DRIVER は、エラー コードと共に制御が返された場合にのみアンロードされます。 EFI_ROM イメージは ROM から実行されます。 詳細については、[統合 EFI フォーラム](https://www.uefi.org/)web サイトの仕様を参照してください。

**な**<br/>
サブシステム環境なしで実行されるコード、たとえばカーネル モード デバイス ドライバーやネイティブ システム プロセス。 このオプションは、通常、Windows システムの機能のために予約されています。

**ビリ**<br/>
Windows 上の POSIX サブシステムで実行するアプリケーション。

**ウィンドウ**<br/>
Windows のグラフィカル環境で実行するアプリケーション。 これには、デスクトップアプリとユニバーサル Windows プラットフォーム (UWP) アプリの両方が含まれます。

**WINDOWSCE**<br/>
WINDOWSCE サブシステムは、アプリケーションが Windows CE カーネルのバージョンがあるデバイスで実行するように設計されたことを示します。 カーネルのバージョンには、PocketPC、Windows Mobile、Windows Phone 7、Windows CE V1.0-6.0R3、および Windows Embedded Compact 7 があります。

`major` および `minor` 値 (省略可能) で、指定したサブシステムの必要最低バージョンを指定します。

- バージョン番号の整数部 (小数点の左側) は、`major` で指定します。

- バージョン番号の小数部 (小数点の右側) は、`minor` で指定します。

- `major` と `minor` で指定できる値は、0 ～ 65,535 の範囲です。

選択したサブシステムに応じて、プログラムの既定の開始アドレスも変わります。 詳細については、「 [/entry (エントリポイントシンボル)](entry-entry-point-symbol.md)」、「リンカー/entry:*function*オプション」を参照してください。

各サブシステムのメジャーバージョン番号とマイナーバージョン番号の最小値と既定値を含む詳細については、 [/SUBSYSTEM](subsystem-specify-subsystem.md)リンカーオプションを参照してください。

## <a name="see-also"></a>参照

[EDITBIN オプション](editbin-options.md)

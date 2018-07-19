---
title: プロファイル ガイド付き最適化のための環境変数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- profile-guided optimizations, environment variables
ms.assetid: f95a6d1e-49a4-4802-a144-092026b600a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19edc9c8a2702e5b7ac9ae4a49364718f19d3900
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379446"
---
# <a name="environment-variables-for-profile-guided-optimizations"></a>ガイド付き最適化のプロファイルの環境変数

作成されたイメージのテスト シナリオに影響する次の 3 つの環境変数がある **/LTCG:PGI**プロファイル ガイド付き最適化の。

- **PogoSafeMode**アプリケーションのプロファイリングに高速モードとセーフ モードを使用するかどうかを指定します。

- **VCPROFILE_ALLOC_SCALE**プロファイラーで使用するための追加のメモリを追加します。

- **VCPROFILE_PATH** .pgc ファイルを使用するフォルダーを指定することができます。

**PogoSafeMode および VCPROFILE_ALLOC_SCALE 環境変数は、Visual Studio 2015 以降では推奨されません。** リンカー オプション[/GENPROFILE または/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)と[/USEPROFILE](useprofile.md)これらの環境変数として同じリンカー動作を指定します。

## <a name="pogosafemode"></a>PogoSafeMode

この環境変数は推奨されません。 使用して、 **EXACT**または**noexact は、** 引数 **/GENPROFILE**または **/FASTGENPROFILE**この動作を制御します。

オフに設定するか、 **PogoSafeMode** x86 でプロファイリングをアプリケーションに高速モードとセーフ モードを使用するかどうかを指定する環境変数のシステムです。

最適化のガイド付きプロファイル (PGO) では、2 つのモードを持つ、プロファイリング フェーズ:*高速モード*と*セーフ モード*です。 使用して高速モードでプロファイリングを行う、ときに、 **INC**命令データ カウンター数を増やします。 **INC**命令は高速ですが、スレッド セーフではありません。 使用してプロファイリングをセーフ モードでは、ときに、 **LOCK INC**命令データ カウンター数を増やします。 **LOCK INC**命令と同じ機能を持つ、 **INC**命令があり、スレッド セーフですよりも低速、 **INC**命令します。

既定では、PGO プロファイリングは高速モードで動作します。 **PogoSafeMode**がセーフ モードを使用するかどうかにのみ必要です。

PGO プロファイリングをセーフ モードでを実行する、環境変数を使用する必要がありますか、 **PogoSafeMode**かリンカー スイッチ **/PogoSafeMode**、システムによって異なります。 x64 コンピューターでプロファイリングを実行する場合は、リンカー スイッチを使用する必要があります。 X86 でプロファイリングを実行するかどうか、コンピューター、リンカーを使用することは切り替えるか、設定、 **PogoSafeMode**は最適化プロセスを開始する前に、任意の値を環境変数。

### <a name="pogosafemode-syntax"></a>PogoSafeMode 構文

> **set PogoSafeMode**[**=**_value_]

設定**PogoSafeMode**をセーフ モードを有効にするには、その値にします。 値を前の値をクリアし、高速モードを再度有効にせずに設定します。

## <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE

この環境変数は推奨されません。 使用して、 **MEMMIN**と**MEMMAX**引数 **/GENPROFILE**または **/FASTGENPROFILE**この動作を制御します。

変更、 **VCPROFILE_ALLOC_SCALE**プロファイル データを保持するメモリの量を変更する環境変数が割り当てられます。 まれなケースではありません十分なメモリをサポートするために使用可能なテストのシナリオを実行している場合は、プロファイル データを収集します。 ような場合、メモリの量を増やすを設定して**VCPROFILE_ALLOC_SCALE**です。 十分なメモリがあることを示すテストの実行中にエラー メッセージを受信する場合より大きい値を割り当てる**VCPROFILE_ALLOC_SCALE**テストの実行がメモリ不足のエラーなく完了するまでです。

### <a name="vcprofileallocscale-syntax"></a>VCPROFILE_ALLOC_SCALE 構文

> **set VCPROFILE_ALLOC_SCALE**[__=__*scale_value*]

*Scale_value*パラメーターは、テスト シナリオの実行対象とするメモリの量、スケール ファクター。  既定値は 1 です。 たとえば、このコマンド ラインでは、スケール ファクターが 2 に設定します。

`set VCPROFILE_ALLOC_SCALE=2`

## <a name="vcprofilepath"></a>VCPROFILE_PATH

使用して、 **VCPROFILE_PATH** .pgc ファイルを作成するディレクトリを指定する環境変数。 既定では、.pgc ファイルは、プロファイリング対象のバイナリと同じディレクトリに作成されます。 ただし、バイナリの絶対パスが存在しない場合、バイナリが構成されているとは異なるマシンでプロファイルのシナリオを実行すると、大文字と小文字をすることがある、設定できます**VCPROFILE_PATH**ターゲット コンピューター上に存在するパスにします。

### <a name="vcprofilepath-syntax"></a>VCPROFILE_PATH 構文

> **set VCPROFILE_PATH**[**=**_path_]

設定、*パス*.pgc ファイルを追加するディレクトリ パスへのパラメーターです。 たとえば、次のコマンドラインは、C:\profile にフォルダーを設定します。

`set VCPROFILE_PATH=c:\profile`

## <a name="see-also"></a>関連項目

[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)<br/>
[/GENPROFILE と/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/USEPROFILE](useprofile.md)<br/>

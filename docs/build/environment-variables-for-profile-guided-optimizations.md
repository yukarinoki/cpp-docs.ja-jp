---
title: ガイド付き最適化のプロファイルの環境変数
ms.date: 03/14/2018
helpviewer_keywords:
- profile-guided optimizations, environment variables
ms.assetid: f95a6d1e-49a4-4802-a144-092026b600a3
ms.openlocfilehash: 099e57f1ac69223adafe7bec1af4cc3452915e86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195274"
---
# <a name="environment-variables-for-profile-guided-optimizations"></a>ガイド付き最適化のプロファイルの環境変数

ガイド付き最適化のプロファイルでは、 **/LTCG:PGI** で作成されるイメージでテスト シナリオに影響を与える環境変数が 3 つあります。

- **PogoSafeMode** では、アプリケーションのプロファイリングに高速モードとセーフ モードのどちらを使用するかを指定します。

- **VCPROFILE_ALLOC_SCALE** では、プロファイラーが使用するためのメモリが追加されます。

- **VCPROFILE_PATH** では、.pgc ファイルで使用されるフォルダーを指定できます。

**The PogoSafeMode and VCPROFILE_ALLOC_SCALE 環境変数は Visual Studio 2015 より非推奨になっています。** リンカー オプションの [/GENPROFILE または /FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) および [/USEPROFILE](reference/useprofile.md) では、これらの環境変数と同じリンカー動作が指定されます。

## <a name="pogosafemode"></a>PogoSafeMode

この環境変数は非推奨です。 **EXACT** または **NOEXACT** 引数を **/GENPROFILE** または **/FASTGENPROFILE** に使用し、この動作を制御します。

**PogoSafeMode** 環境変数を解除するか設定し、x86 システムのアプリケーション プロファイルで高速モードを使用するか、セーフ モードを使用するか指定します。

ガイド付き最適化のプロファイル (PGO: Profile-Guided Optimization) では、プロファイリング フェーズで*高速モード*と*セーフ モード*の 2 つのモードを使用できます。 高速モードでプロファイリングを行う場合は、**INC** 命令を使用してデータ カウンター数を増やします。 **INC** 命令は高速ですが、スレッド セーフではありません。 セーフ モードでプロファイリングを行う場合は、**LOCK INC** 命令を使用してデータ カウンター数を増やします。 **LOCK INC** 命令は **INC** 命令と同じ機能を持ち、スレッド セーフですが、**INC** 命令より低速です。

既定では、PGO プロファイリングは高速モードで動作します。 **PogoSafeMode** は、セーフ モードを使用する場合にのみ必要です。

PGO プロファイリングをセーフ モードで実行するには、システムに応じて、環境変数 **PogoSafeMode** かリンカー スイッチ **/PogoSafeMode** のどちらかを使用する必要があります。 x64 コンピューターでプロファイリングを実行する場合は、リンカー スイッチを使用する必要があります。 x86 コンピューターでプロファイリングを実行する場合は、最適化処理を開始する前に、リンカー スイッチを使用するか、**PogoSafeMode** 環境変数を任意の値に設定できます。

### <a name="pogosafemode-syntax"></a>PogoSafeMode 構文

> **set PogoSafeMode**[ **=** _value_]

**PogoSafeMode** を任意の値に設定し、セーフ モードを有効にします。 値なしで設定すると、前の値が解除され、高速モードが再び有効になります。

## <a name="vcprofile_alloc_scale"></a>VCPROFILE_ALLOC_SCALE

この環境変数は非推奨です。 **MEMMIN** および **MEMMAX** 引数を **/GENPROFILE** または **/FASTGENPROFILE** に使用し、この動作を制御します。

**VCPROFILE_ALLOC_SCALE** 環境変数を変更し、プロファイル データを保持するために割り当てられるメモリ量を変更します。 テスト シナリオの実行時、メモリが足りず、プロファイル データを収集できないことがまれにあります。 そのような場合、**VCPROFILE_ALLOC_SCALE** を設定し、メモリ量を増加できます。 テスト実行中、エラー メッセージが表示され、メモリが足りないことが判明した場合、メモリ不足エラーなしでテスト実行が完了されるまで、**VCPROFILE_ALLOC_SCALE** に割り当てる値を大きくしてください。

### <a name="vcprofile_alloc_scale-syntax"></a>VCPROFILE_ALLOC_SCALE 構文

> **set VCPROFILE_ALLOC_SCALE**[ __=__ *scale_value*]

*scale_value* パラメーターは、テスト シナリオの実行に必要なメモリ量を調整するパラメーターです。  既定値は 1 です。 たとえば、次のコマンド ラインではスケール ファクターが 2 に設定されます。

`set VCPROFILE_ALLOC_SCALE=2`

## <a name="vcprofile_path"></a>VCPROFILE_PATH

**VCPROFILE_PATH** 環境変数を使用し、.pgc ファイルを作成するディレクトリを指定します。 既定では、.pgc プロファイルはプロファイリング中のバイナリと同じディレクトリで作成されます。 ただし、バイナリが構築されたコンピューターとは別のコンピューターでプロファイル シナリオを実行するときにあることですが、バイナリの絶対パスが存在しない場合、ターゲット コンピューターに存在するパスに **VCPROFILE_PATH** を設定できます。

### <a name="vcprofile_path-syntax"></a>VCPROFILE_PATH 構文

> **set VCPROFILE_PATH**[ **=** _path_]

.pgc ファイルを追加するディレクトリ パスに *path* パラメーターを設定します。 たとえば、このコマンド ラインではフォルダーが C:\profile に設定されます。

`set VCPROFILE_PATH=c:\profile`

## <a name="see-also"></a>関連項目

[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)<br/>
[/GENPROFILE と /FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/USEPROFILE](reference/useprofile.md)<br/>

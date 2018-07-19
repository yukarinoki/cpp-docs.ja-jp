---
title: pgosweep |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ded5b692d7c51e5a46a325a69ad6969083025ff5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378926"
---
# <a name="pgosweep"></a>pgosweep

.Pgc ファイルに、実行中のプログラムからすべてのプロファイル データを書き込めませんプロファイル ガイド付き最適化のために使用します。

## <a name="syntax"></a>構文

> **pgosweep** [*オプション*]*イメージ* *pgcfile*

### <a name="parameters"></a>パラメーター

*オプション*(省略可能)<br/>
有効値、*オプション*は。

- **/?** または **/help**ヘルプ メッセージが表示されます。

- **/noreset**ランタイム データ構造体に含まれる数を保持します。

*image*<br/>
使用して作成された .exe または .dll ファイルの完全なパス、 [/GENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)、 [/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)、または[/LTCG:PGINSTRUMENT](ltcg-link-time-code-generation.md)オプション。

*pgcfile*<br/>
.Pgc ファイルは、このコマンドの書き込み先データをカウントします。

## <a name="remarks"></a>コメント

**Pgosweep**コマンドを使用してビルドされたプログラムで機能、 [/GENPROFILE または/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)オプション、または、非推奨[/LTCG:PGINSTRUMENT](ltcg-link-time-code-generation.md)オプション。 これにより、実行中のプログラムを中断し、新しい .pgc ファイルにプロファイル データを書き込みます。 既定では、コマンドは、個々 の書き込み操作の後にカウントをリセットします。 指定した場合、 **/noreset**オプション、コマンドは、値が記録されますが、プログラムの実行にリセットされません。 このオプションを提供するデータの重複した後で、プロファイル データを取得する場合。

用途**pgosweep**だけ、アプリケーションの通常の動作のプロファイル情報を取得することです。 たとえば、実行する**pgosweep**すぐにアプリケーションを起動し、そのファイルを破棄します。 これは、スタートアップ コストに関連付けられているプロファイル データを削除します。 その後、実行**pgosweep**アプリケーションを終了する前にします。 収集されたデータになりました、ユーザーがプログラムで相互作用するだけの時間のプロファイル情報。

.Pgc ファイル名を指定する場合 (を使用して、 *pgcfile*パラメーター) は、標準の形式を使用する*appname! n*.pgc です。 この形式を使用する場合、コンパイラがでこのデータを自動的に検出、 **/LTCG/USEPROFILE**または **/LTCG:PGO**フェーズ。 使用する必要があります、標準の形式を使用しない場合[pgomgr](pgomgr.md) .pgc ファイルをマージします。

> [!NOTE]
> このツールは、Visual Studio 開発者コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。

実行可能ファイル内からプロファイル データをキャプチャする方法については、次を参照してください。 [PgoAutoSweep](pgoautosweep.md)です。

## <a name="example"></a>例

この例では、 **pgosweep** myapp!1.pgc に myapp.exe の現在のプロファイル情報を書き込みます。

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>関連項目

[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>

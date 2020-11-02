---
title: pgosweep
description: pgosweep コマンドを使用して、ガイド付き最適化のプロファイルで使用するためにプロファイル データを PGC ファイルに書き込みます。
ms.date: 10/23/2020
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.openlocfilehash: be96d0f092ff65867c304ddf5eb41c0754f6e4be
ms.sourcegitcommit: bf54b407169900bb668c85a67b31dbc0f069fe65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92497180"
---
# <a name="pgosweep"></a>pgosweep

ガイド付き最適化のプロファイルで、実行中のプログラムから PGC ファイルにすべてのプロファイル データを書き込むために使用されます。

## <a name="syntax"></a>構文

> **`pgosweep`** [ *options* ] *image* *pgcfile*

### <a name="parameters"></a>パラメーター

*options*\
(省略可能) *options* の有効な値は次のとおりです。

- **`/?`** または **`/help`** : ヘルプ メッセージを表示します。

- **`/reset`** : スイープ後にカウントを 0 にリセットします。 これが既定の動作となります。

- **`/pid:n`** : 指定した PID だけをスイープします。 *n* は PID 番号です。

- **`/wait`** : 指定した PID が終了するまで待機してからカウントを収集します。

- **`/onlyzero`** PGC ファイルを保存せず、カウントを 0 にします。

- **`/pause`** : システムのカウント収集を一時停止します。

- **`/resume`** : システムのカウント収集を再開します。

- **`/noreset`** : ランタイム データ構造体にカウントを保持します。

*image*\
[`/GENPROFILE`](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)、[`/FASTGENPROFILE`](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)、または [`/LTCG:PGINSTRUMENT`](reference/ltcg-link-time-code-generation.md) オプションを使用して作成された EXE または DLL ファイルの完全なパス。

*pgcfile*\
このコマンドによってデータ カウントが書き込まれる PGC ファイル。

## <a name="remarks"></a>解説

**`pgosweep`** コマンドは、[`/GENPROFILE` または `/FASTGENPROFILE`](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) オプション、または非推奨の [`/LTCG:PGINSTRUMENT`](reference/ltcg-link-time-code-generation.md) オプションを使用して作成されたプログラムで機能します。 実行中のプログラムが中断され、プロファイル データが新しい PGC ファイルに書き込まれす。 既定では、コマンドでは各書き込み操作の後にカウントがリセットされます。 **`/noreset`** オプションを指定すると、コマンドにより値が記録されますが、実行中のプログラム内で値はリセットされません。 このオプションを使用すると、後でプロファイル データを取得した場合にデータが重複します。

**`pgosweep`** の別の用途は、アプリケーションの通常の操作用にのみプロファイル情報を取得することです。 たとえば、アプリケーションを起動してそのファイルを破棄した後すぐに、 **`pgosweep`** を実行できます。 このコマンドにより、スタートアップ コストに関連するプロファイル データが削除されます。 次に、アプリケーションを終了する前に **`pgosweep`** を実行できます。 これで、収集されたデータには、ユーザーがプログラムと対話できたときのプロファイル情報のみが含まれるようになります。

PGC ファイルに ( *pgcfile* パラメーターを使用して) 名前を指定する場合、標準形式 ( *`appname!n.pgc`* ) を使用できます。 *n* は、各ファイルの増加する数値を表します。 この形式を使用すると、コンパイラによりこのデータが **`/LTCG /USEPROFILE`** または **`/LTCG:PGO`** フェーズで自動的に検出されます。 標準形式を使用しない場合は、[`pgomgr`](pgomgr.md) を使用して PGC ファイルをマージする必要があります。

> [!NOTE]
> このツールは Visual Studio 開発者コマンド プロンプトからのみ起動できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。

実行可能ファイル内からプロファイル データをキャプチャする方法の詳細については、「[`PgoAutoSweep`](pgoautosweep.md)」を参照してください。

## <a name="example"></a>例

この例のコマンドでは、 **`pgosweep`** によって *`myapp.exe`* の現在のプロファイル情報が *`myapp!1.pgc`* に書き込まれます。

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>関連項目

[プロファイルに基づく最適化](profile-guided-optimizations.md)\
[PgoAutoSweep](pgoautosweep.md)

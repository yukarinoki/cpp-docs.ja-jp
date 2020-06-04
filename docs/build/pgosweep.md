---
title: pgosweep
ms.date: 03/14/2018
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
ms.openlocfilehash: 3ba31671fc3794e1cc959d86d914ba1eef2e01e4
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341198"
---
# <a name="pgosweep"></a>pgosweep

ガイド付き最適化のプロファイルで、実行中のプログラムから .pgc ファイルにすべてのプロファイル データを書き込むために使用されます。

## <a name="syntax"></a>構文

> **pgosweep** [*options*] *image* *pgcfile*

### <a name="parameters"></a>パラメーター

*options*<br/>
(省略可能) *options* の有効な値は次のとおりです。

- **/?** または **/help** を指定すると、ヘルプ メッセージを表示します。

- **/noreset** を指定すると、ランタイム データ構造体にカウントを保持します。

*イメージ*<br/>
[/GENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)、[/FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)、または [/LTCG:PGINSTRUMENT](reference/ltcg-link-time-code-generation.md) オプションを使用して作成された .exe ファイルまたは .dll ファイルの完全パス。

*pgcfile*<br/>
このコマンドによってデータ カウントが書き込まれる .pgc ファイル。

## <a name="remarks"></a>Remarks

**pgosweep** コマンドは、[/GENPROFILE または /FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) オプション、または非推奨の [/LTCG:PGINSTRUMENT](reference/ltcg-link-time-code-generation.md) オプションを使用して構築されたプログラムで機能します。 実行中のプログラムが中断され、プロファイル データが新しい .pgc ファイルに書き込まれす。 既定では、コマンドでは各書き込み操作の後にカウントがリセットされます。 **/noreset** オプションを指定すると、コマンドにより値が記録されますが、実行中のプログラム内で値はリセットされません。 このオプションを使用すると、後でプロファイル データを取得した場合にデータが重複します。

**pgosweep** の別の用途は、アプリケーションの通常の操作用にのみプロファイル情報を取得することです。 たとえば、アプリケーションを起動してそのファイルを破棄した後すぐに、**pgosweep** を実行できます。 これにより、スタートアップ コストに関連するプロファイル データが削除されます。 次に、アプリケーションを終了する前に **pgosweep** を実行できます。 これで、収集されたデータには、ユーザーがプログラムと対話できたときのプロファイル情報のみが含まれるようになります。

.pgc ファイルに (*pgcfile* パラメーターを使用して) 名前を指定する場合、標準形式 (*appname!n*.pgc) を使用できます。 この形式を使用すると、コンパイラによりこのデータが **/LTCG /USEPROFILE** または **/LTCG:PGO** フェーズで自動的に検出されます。 標準形式を使用しない場合は、[pgomgr](pgomgr.md) を使用して .pgc ファイルをマージする必要があります。

> [!NOTE]
> このツールは Visual Studio 開発者コマンド プロンプトからのみ起動できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。

実行可能ファイル内からプロファイル データをキャプチャする方法の詳細については、「[PgoAutoSweep](pgoautosweep.md)」を参照してください。

## <a name="example"></a>例

この例のコマンドでは、**pgosweep** によって myapp.exe の現在のプロファイル情報が myapp!1.pgc に書き込まれます。

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>関連項目

[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>

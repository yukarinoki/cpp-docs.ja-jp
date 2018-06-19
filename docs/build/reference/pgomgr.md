---
title: pgomgr |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bf7567cfe9f21effda913606ca3af9a19464f9d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377207"
---
# <a name="pgomgr"></a>pgomgr

.Pgd ファイルを 1 つまたは複数の .pgc ファイルからプロファイル データを追加します。

## <a name="syntax"></a>構文

> **pgomgr** [*options*] *pgcfiles* *pgdfile*

### <a name="parameters"></a>パラメーター

*options*<br/>
次のオプションを指定できます**pgomgr**:

- **/help**または **/しますか?** 使用可能な表示**pgomgr**オプション。

- **/clear** .pgd ファイルすべてのプロファイル情報をクリアします。 .Pgc を指定することはできませんファイル **/clear**を指定します。

- **/detail**フロー グラフのカバレッジ情報を含む、詳細な統計情報を表示します。

- **/summary**表示関数ごとの統計情報。

- **一意/** と共に使用する場合 **/summary**原因、装飾関数名を表示します。 既定値、**一意/** は使用しない場合、装飾されていない関数名が表示されますが、します。

- **/merge**[**: * * * n*] は、.pgc ファイルまたは .pgd ファイルを追加するファイルのデータ。 省略可能なパラメーター、 *n*、データを追加することを指定する*n*回です。 たとえばがの場合、シナリオよく 6 回を元に戻すことが顧客によって行うはどのくらいの頻度を反映するように、テストの実行で 1 回行うことして 6 回 .pgd ファイルに追加**した後**です。

*pgcfiles*<br/>
1 つまたは複数の .pgc ファイルの .pgd ファイルにマージするプロファイル データを含むです。 単一 .pgc ファイルまたは複数の .pgc ファイルを指定することができます。 .Pgc ファイルをすべて指定しない場合**pgomgr** .pgd ファイルと同じファイル名を持つ、すべての .pgc ファイルをマージします。

*pgdfile* .pgc ファイルまたはファイルからデータをマージ先 .pgd ファイルです。

## <a name="remarks"></a>コメント

> [!NOTE]
> このツールは、Visual Studio 開発者コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。

## <a name="example"></a>例

この例のコマンドは、プロファイル データの myapp.pgd ファイルをクリアします。

`pgomgr /clear myapp.pgd`

この例のコマンドに追加しますプロファイル データ myapp1.pgc .pgd ファイルを 3 回。

`pgomgr /merge:3 myapp1.pgc myapp.pgd`

この例ではすべて myapp!#.pgc ファイルからのプロファイル データが myapp.pgd ファイルに追加されます。

`pgomgr -merge myapp1.pgd`

## <a name="see-also"></a>関連項目

[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgosweep](pgosweep.md)<br/>

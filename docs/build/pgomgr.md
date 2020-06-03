---
title: pgomgr
ms.date: 03/14/2018
helpviewer_keywords:
- pgomgr program
- profile-guided optimizations, pgomgr
ms.assetid: 74589126-df18-42c9-8739-26d60e148d6a
ms.openlocfilehash: 4e3eb08c88db9d0ed4e47649014a600c3e0ccb78
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295254"
---
# <a name="pgomgr"></a>pgomgr

1 つまたは複数の .pgc ファイルから .pgd ファイルにプロファイル データを追加します。

## <a name="syntax"></a>構文

> **pgomgr** [*options*] *pgcfiles* *pgdfile*

### <a name="parameters"></a>パラメーター

*options*<br/>
次のオプションを **pgomgr** に指定できます。

- **/help** または **/?** 利用できる **pgomgr** オプションを表示します。

- **/clear** .pgd ファイルからすべてのプロファイル情報が消去されます。 **/clear** の指定時は .pgc ファイルを指定できません。

- **/detail** フロー グラフ カバレッジ情報など、詳しい統計を表示します。

- **/summary** 関数別の統計を表示します。

- **/unique** **/summary** と併用すると、修飾された関数名が表示されます。 **/unique** を使用しないとき、既定で、修飾のない関数名が表示されます。

- **/merge**\[ **:** <em>n</em>] .pgc ファイルのデータが .pgd ファイルに追加されます。 オプション パラメーター *n* を使用すると、データが *n* 回追加されるように指定できます。 たとえば、顧客により行われる頻度を反映する目的で、あるシナリオを通常 6 回行う場合、それをテスト実行で 1 回行い、**pgomgr /merge:6** で .pgd ファイルに 6 回追加できます。

*pgcfiles*<br/>
プロファイル データを .pgd ファイルに結合する 1 つまたは複数の .pgc ファイル。 1 つの .pgc ファイルか複数の .pgc ファイルを指定できます。 .pgc ファイルを指定しない場合、**pgomgr** では、ファイル名が .pgd ファイルと同じ .pgc ファイルがすべて結合されます。

*pgdfile*<br/>
.pgc ファイル データの結合先となる .pgd ファイル。

## <a name="remarks"></a>Remarks

> [!NOTE]
> このツールは Visual Studio 開発者コマンド プロンプトからのみ起動できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。

## <a name="example"></a>例

このサンプル コマンドでは、プロファイル データの myapp ファイルが消去されます。

`pgomgr /clear myapp.pgd`

このサンプル コマンドでは、myapp1.pgc のプロファイル データが .pgd ファイルに 3 回追加されます。

`pgomgr /merge:3 myapp1.pgc myapp.pgd`

このサンプルでは、すべての myapp#.pgc ファイルからのプロファイル データが myapp.pgd ファイルに追加されます。

`pgomgr -merge myapp1.pgd`

## <a name="see-also"></a>関連項目

[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgosweep](pgosweep.md)<br/>

---
title: Tools.ini と NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
ms.openlocfilehash: c50fef5d2fd36b8fb9327cad25bc5b2ab4ba61e2
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419885"
---
# <a name="toolsini-and-nmake"></a>Tools.ini と NMAKE

NMAKE 読み取ります Tools.ini、メイクファイルを読み取る前に/R を使用しない場合。 検索 Tools.ini まず現在のディレクトリにし、INIT 環境変数で指定されたディレクトリにします。 初期化ファイル (nmake の) 設定セクションの先頭で`[NMAKE]`メイクファイル情報を含めることができます。 番号記号で個別の行の先頭にコメントを指定 (#)。

## <a name="see-also"></a>関連項目

[NMAKE の実行](../build/running-nmake.md)

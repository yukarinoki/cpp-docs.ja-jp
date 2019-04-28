---
title: NMAKE の実行
ms.date: 09/05/2018
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
ms.openlocfilehash: dac5e9c1676278d150dd9802697a8ae8959a40e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318526"
---
# <a name="running-nmake"></a>NMAKE の実行

## <a name="syntax"></a>構文

> **NMAKE** [*オプション*...][*マクロ*...][*ターゲット*...][**\@**<em>commandfile</em> ...]

## <a name="remarks"></a>Remarks

のみ指定 (nmake の) ビルド*ターゲット*または、1 つ目がメイクファイルでターゲット指定されていない場合。 最初のメイクファイル ターゲットを指定できます、[疑似ターゲット](pseudotargets.md)他のターゲットをビルドします。 (Nmake の) は、/F; で指定されたメイクファイルを使用します。/F が指定されていない場合は、現在のディレクトリにメイクファイルのファイルが使用されます。 コマンド ライン ビルドを推論規則を使用して、メイクファイルが指定されていない場合*ターゲット*します。

*Commandfile*テキスト ファイル (または応答ファイル) は、コマンドラインの入力が含まれています。 その他の入力が前または後\@ *commandfile*します。 パスが許可されます。 *Commandfile*改行はスペースとして扱われます。 スペースが含まれている場合は、マクロ定義を引用符で囲みます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

[NMAKE のオプション](nmake-options.md)

[Tools.ini と NMAKE](tools-ini-and-nmake.md)

[NMAKE で返される終了コード](exit-codes-from-nmake.md)

## <a name="see-also"></a>関連項目

[NMAKE リファレンス](nmake-reference.md)

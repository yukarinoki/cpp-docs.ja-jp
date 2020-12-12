---
description: 詳細情報:/追加
title: /ALLOWISOLATION
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION_EDITBIN
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
ms.openlocfilehash: 7d935bc122b5f32bb8f1193feae58b5fc61e7faa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179591"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

マニフェスト検索の動作を指定します。

## <a name="syntax"></a>構文

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>解説

また、オペレーティングシステムはマニフェストの参照と読み込みを実行します。

これ **が既定値です。**

または、[**いいえ**] に設定すると、実行可能ファイルがマニフェストがないかのように読み込まれ、 [EDITBIN 参照](editbin-reference.md)によって `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` 省略可能なヘッダーのフィールドにビットが設定され `DllCharacteristics` ます。

実行可能ファイルの分離が無効の場合、Windows ローダーは、新しく作成されたプロセスに対応するアプリケーション マニフェストの検索を試行しません。 新しいプロセスには、実行可能ファイル自体にマニフェストがある場合や、 *実行可能ファイル* という名前のマニフェストがある場合でも、既定のアクティベーションコンテキストがありません。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](editbin-options.md)<br/>
[/自動 (マニフェスト参照)](allowisolation-manifest-lookup.md)<br/>
[マニフェストファイルのリファレンス](/windows/win32/SbsCs/manifest-files-reference)

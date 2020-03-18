---
title: /ALLOWISOLATION
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION_EDITBIN
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
ms.openlocfilehash: 3dae8ee83e25492fab0ba2c6a55681728d5f3453
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440372"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

マニフェスト検索の動作を指定します。

## <a name="syntax"></a>構文

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>コメント

**/ALLOWISOLATION**また、オペレーティングシステムはマニフェストの参照と読み込みを実行します。

これ**が既定値です。**

(& A) **: NO**は、マニフェストがないかのように実行可能ファイルが読み込まれることを示します。また、 [EDITBIN 参照](editbin-reference.md)によって、省略可能なヘッダーの `DllCharacteristics` フィールドに `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` ビットが設定されます。

実行可能ファイルの分離が無効の場合、Windows ローダーは、新しく作成されたプロセスに対応するアプリケーション マニフェストの検索を試行しません。 新しいプロセスには、実行可能ファイル自体にマニフェストがある場合や、*実行可能ファイル*という名前のマニフェストがある場合でも、既定のアクティベーションコンテキストがありません。

## <a name="see-also"></a>参照

[EDITBIN オプション](editbin-options.md)<br/>
[/ALLOWISOLATION (マニフェスト検索)](allowisolation-manifest-lookup.md)<br/>
[マニフェストファイルのリファレンス](/windows/win32/SbsCs/manifest-files-reference)

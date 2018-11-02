---
title: /ALLOWISOLATION
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
ms.openlocfilehash: ab07e3ac3f8c154ffa62a25ab8bad967b255e2e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604973"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

マニフェスト検索の動作を指定します。

## <a name="syntax"></a>構文

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Remarks

**/ALLOWISOLATION**により、オペレーティング システムはマニフェストの検索と読み込みをします。

**/ALLOWISOLATION**既定値です。

**/ALLOWISOLATION:NO**マニフェスト、およびエラーの原因がない場合に、実行可能ファイルが読み込まれていることを示します[EDITBIN リファレンス](../../build/reference/editbin-reference.md)を設定する、 `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` 、オプションのヘッダー内のビット`DllCharacteristics`フィールド。

実行可能ファイルの分離が無効の場合、Windows ローダーは、新しく作成されたプロセスに対応するアプリケーション マニフェストの検索を試行しません。 自体の実行可能ファイルにマニフェストがあるか、名前を持つ場合は、マニフェストがある場合でも、新しいプロセスは既定のアクティベーション コンテキストにない*実行可能ファイル名*。 exe.manifest します。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](../../build/reference/editbin-options.md)<br/>
[/ALLOWISOLATION (マニフェスト検索)](../../build/reference/allowisolation-manifest-lookup.md)<br/>
[マニフェスト ファイルのリファレンス](/windows/desktop/SbsCs/manifest-files-reference)
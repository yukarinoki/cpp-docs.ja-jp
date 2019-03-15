---
title: STUB
ms.date: 11/04/2016
f1_keywords:
- STUB
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
ms.openlocfilehash: 5224fdaa2a03dc615c9e7e7bb7f7ba822a40807e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822120"
---
# <a name="stub"></a>STUB

仮想デバイス ドライバー (VxD) (WINNT で定義されている IMAGE_DOS_HEADER 構造体を含むファイル名を指定することができますを構築するモジュール定義ファイルで使用する場合。H) をクリックし、既定のヘッダーではなく、仮想デバイス ドライバー (VxD) で使用します。

```
STUB:filename
```

## <a name="remarks"></a>Remarks

指定するのと同じ方法*filename*では、 [/stub](stub-ms-dos-stub-file-name.md)リンカー オプション。

スタブは VxD を構築する場合だけ、モジュール定義ファイルで有効です。

## <a name="see-also"></a>関連項目

[モジュール定義ステートメントに関する規則](rules-for-module-definition-statements.md)

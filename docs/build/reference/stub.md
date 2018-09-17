---
title: スタブ |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STUB
dev_langs:
- C++
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 151d7b425a7f397a05e3a06e9d94489a0c76f899
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725115"
---
# <a name="stub"></a>STUB

仮想デバイス ドライバー (VxD) (WINNT で定義されている IMAGE_DOS_HEADER 構造体を含むファイル名を指定することができますを構築するモジュール定義ファイルで使用する場合。H) をクリックし、既定のヘッダーではなく、仮想デバイス ドライバー (VxD) で使用します。

```
STUB:filename
```

## <a name="remarks"></a>Remarks

指定するのと同じ方法*filename*では、 [/stub](../../build/reference/stub-ms-dos-stub-file-name.md)リンカー オプション。

スタブは VxD を構築する場合だけ、モジュール定義ファイルで有効です。

## <a name="see-also"></a>関連項目

[モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)
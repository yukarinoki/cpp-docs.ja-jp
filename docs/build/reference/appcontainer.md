---
title: -APPCONTAINER |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /APPCONTAINER
dev_langs:
- C++
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d8e19724183963329b959286a996b4f21d18b4c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709184"
---
# <a name="appcontainer"></a>/APPCONTAINER

アプリケーション コンテナーで実行する必要がある実行可能ファイル、たとえば、Microsoft Store またはユニバーサル Windows アプリ。

```

/APPCONTAINER[:NO]
```

## <a name="remarks"></a>Remarks

**/APPCONTAINER** のオプション セットがある実行可能ファイルは、Windows 8 で導入されたプロセス分離環境であるアプリケーション コンテナーでのみ実行できます。 Microsoft Store およびユニバーサル Windows アプリの場合、このオプションを設定する必要があります。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](../../build/reference/editbin-options.md)<br/>
[ユニバーサル Windows アプリとは何ですか。](/windows/uwp/get-started/universal-application-platform-guide)
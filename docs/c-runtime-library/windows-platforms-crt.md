---
title: Windows プラットフォーム (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility [C++], C run-time libraries
- compatibility [C++], C run-time libraries
- MBCS [C++], Win32 platforms
- operating systems [C++]
- Unicode [C++], Win32 platforms
ms.assetid: 0aacaf45-6dc4-4908-bd52-57abac7b39f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29976d0535d29fce926d7a12b920234548c8a98d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017290"
---
# <a name="windows-platforms-crt"></a>Windows プラットフォーム (CRT)

Visual Studio の C ランタイム ライブラリでは最新バージョンの Windows と Windows Server、Windows 8、Windows Server 2012、Windows 7、Windows Server 2008、Windows Vista がサポートされ、必要に応じて x86 用の Windows XP Service Pack 3 (SP3)、x64 用の Windows XP Service Pack 2 (SP2)、および x86 と x64 用の Windows Server 2003 Service Pack 2 (SP2) がサポートされます。 これらすべてのオペレーティング システムで、Windows デスクトップ API (Win32) をサポートし、Unicode のサポートを提供します。 さらに、すべての Win32 アプリケーションで、マルチバイト文字セット (MBCS) を使用できます。

> [!NOTE]
> Visual Studio 2017 の **C++ を使用したデスクトップ開発**のワークロードの既定のインストールには、Windows XP と Windows Server 2003 の開発のサポートは含まれていません。 省略可能なコンポーネントである **C++ に関する Windows XP サポート**をインストールして Windows XP プラットフォーム ツールセットを有効にする必要があります。

## <a name="see-also"></a>関連項目

[互換性](../c-runtime-library/compatibility.md)

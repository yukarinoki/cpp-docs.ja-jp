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
ms.openlocfilehash: d53e8020bbb7649d78232025ef9c63c1dc868fee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409008"
---
# <a name="windows-platforms-crt"></a>Windows プラットフォーム (CRT)

Visual Studio の C ランタイム ライブラリは最新バージョンの Windows と Windows Server、[!INCLUDE[win8](../build/reference/includes/win8_md.md)]、[!INCLUDE[winserver8](../build/reference/includes/winserver8_md.md)], [!INCLUDE[win7](../build/includes/win7_md.md)]、[!INCLUDE[winsvr08](../build/reference/includes/winsvr08_md.md)]、Windows Vista をサポートし、必要に応じて x86 用の [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 3 (SP3)、x64 用の [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 2 (SP2)、および x86 と x64 用の [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Service Pack 2 (SP2) をサポートします。 これらすべてのオペレーティング システムで、Windows デスクトップ API (Win32) をサポートし、Unicode のサポートを提供します。 さらに、すべての Win32 アプリケーションで、マルチバイト文字セット (MBCS) を使用できます。

> [!NOTE]
> Visual Studio 2017 の **C++ を使用したデスクトップ開発**のワークロードの既定のインストールには、[!INCLUDE[winxp](../build/includes/winxp_md.md)] と [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] の開発のサポートは含まれていません。 省略可能なコンポーネントである **C++ に関する Windows XP サポート**をインストールして Windows XP プラットフォーム ツールセットを有効にする必要があります。

## <a name="see-also"></a>関連項目

[互換性](../c-runtime-library/compatibility.md)  

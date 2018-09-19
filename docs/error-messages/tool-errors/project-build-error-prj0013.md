---
title: プロジェクト ビルド エラー PRJ0013 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0013
dev_langs:
- C++
helpviewer_keywords:
- PRJ0013
ms.assetid: 95e7bafd-63c8-4b2d-b778-f19cdf9ba36c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7a151ca34d680a517c405e5cb6f91c18d35bedd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102646"
---
# <a name="project-build-error-prj0013"></a>プロジェクト ビルド エラー PRJ0013

システム リソースが非常に少ない可能性があります。 ビルドの起動に必要なパイプを作成できません。

このエラーは、システム リソースが少ないことを示しています。 このエラーを解決するには、他のプロセス/アプリケーションによるシステム リソースの使用を減らします。

このエラーは、セキュリティ レベルが不十分でパイプを作成する場合は発生も (を参照してください[CreatePipe](https://msdn.microsoft.com/library/windows/desktop/aa365152.aspx))。
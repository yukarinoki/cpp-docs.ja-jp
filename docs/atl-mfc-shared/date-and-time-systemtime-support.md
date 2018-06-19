---
title: '日付と時刻: SYSTEMTIME サポート |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- system time
- FILETIME structure, with CTime class
- time [C++], formatting
- SYSTEMTIME structure
- dates [C++], MFC
- formatting [C++], time
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ecbfd517a0fd535a23920ae21d03f1756babc113
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355401"
---
# <a name="date-and-time-systemtime-support"></a>日付と時刻: SYSTEMTIME サポート
[CTime](../atl-mfc-shared/reference/ctime-class.md)クラスには、Win32 からシステムとファイルの時間を受け入れるコンス トラクターです。 このような目的に `CTime` オブジェクトを使用する場合は、この記事の説明に従って初期化を適宜変更する必要があります。  
  
 SYSTEMTIME 構造体については、次を参照してください。 [SYSTEMTIME](../mfc/reference/systemtime-structure1.md)です。 FILETIME 構造については、次を参照してください。 [FILETIME](../mfc/reference/filetime-structure.md)です。  
  
 MFC では今でも MS-DOS スタイルの時間の引数を受け取る `CTime` コンストラクターが提供されていますが、MFC バージョン 3.0 からは、`CTime` クラスで、Win32 の `SYSTEMTIME` 構造体を受け取るコンストラクターと、Win32 の `FILETIME` 構造体を受け取る別のコンストラクターもサポートされています。  
  
 新しい `CTime` コンストラクターは、次のとおりです。  
  
-   CTime (const SYSTEMTIME & `sysTime`) です。  
  
-   CTime (const FILETIME & `fileTime`) です。  
  
 `fileTime` パラメーターは Win32 の `FILETIME` 構造体への参照で、この構造体は時間を 64 ビット値で表します。`SYSTEMTIME` 構造体よりも内部ストレージに便利な形式で、ファイルの作成時間を表すために Win32 で使用されます。  
  
 システム時刻で初期化された `CTime` オブジェクトがコードに含まれる場合は、Win32 の `SYSTEMTIME` コンストラクターを使用する必要があります。  
  
 多くの場合は使用しません`CTime``FILETIME`直接の初期化します。 使用する場合、`CFile`ファイルを操作するオブジェクト[cfile::getstatus](../mfc/reference/cfile-class.md#getstatus)経由でのファイルのタイムスタンプを取得、`CTime`オブジェクトを初期化して、`FILETIME`構造体。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [MFC の一般的な日付と時刻](../atl-mfc-shared/date-and-time.md)  
  
-   [日付と時刻のオートメーションのサポート](../atl-mfc-shared/date-and-time-automation-support.md)  
  
-   [日付と時刻のプログラミングの汎用クラス](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
## <a name="see-also"></a>関連項目  
 [日付と時刻](../atl-mfc-shared/date-and-time.md)


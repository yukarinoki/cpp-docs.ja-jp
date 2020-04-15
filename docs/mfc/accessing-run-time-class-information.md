---
title: ランタイム クラス情報へのアクセス方法
ms.date: 11/04/2016
helpviewer_keywords:
- CObject class [MFC], and RTTI
- CObject class [MFC], using IsKindOf method [MFC]
- run time [MFC], class information
- RUNTIME_CLASS macro [MFC]
- CObject class [MFC], using RUNTIME_CLASS macro [MFC]
- RTTI compiler option [MFC]
- CObject class [MFC], accessing run-time class information
- run time [MFC]
- IsKindOf method method [MFC]
- run-time class [MFC], accessing information
- classes [MFC], run-time class information
- run-time class [MFC]
- RUNTIME_CLASS macro, using
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
ms.openlocfilehash: 4a836bb7bd03bd6654e5c940442fecf541042fd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354226"
---
# <a name="accessing-run-time-class-information"></a>ランタイム クラス情報へのアクセス方法

この資料では、実行時にオブジェクトのクラスに関する情報にアクセスする方法について説明します。

> [!NOTE]
> MFC では、Visual C++ 4.0 で導入された[ランタイム型情報](../cpp/run-time-type-information.md)(RTTI) のサポートは使用されません。

[CObject](../mfc/reference/cobject-class.md)からクラスを派生し **、Declare**_**DYNAMIC** `IMPLEMENT_DYNAMIC`および 、`DECLARE_DYNCREATE`および`IMPLEMENT_DYNCREATE`を使用`DECLARE_SERIAL`した`IMPLEMENT_SERIAL`場合、または を使用して、CObject[からクラス](../mfc/deriving-a-class-from-cobject.md)を`CObject`派生する」の記事で説明されていると と を使用する場合、クラスは実行時にオブジェクトの正確なクラスを決定する機能を持ちます。

この機能は、関数引数の型チェックが必要な場合や、オブジェクトのクラスに基づいて特別な目的のコードを記述する必要がある場合に最も便利です。 ただし、仮想関数の機能が重複しているため、通常は推奨されません。

メンバー`CObject`関数`IsKindOf`を使用して、特定のオブジェクトが指定したクラスに属しているかどうか、または特定のクラスから派生しているかどうかを判断できます。 引数`IsKindOf`はオブジェクトで`CRuntimeClass`、クラス名の`RUNTIME_CLASS`マクロを使用して取得できます。

### <a name="to-use-the-runtime_class-macro"></a>RUNTIME_CLASS マクロを使用するには

1. クラス`RUNTIME_CLASS`の名前と共に使用します`CObject`。

   [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]

ランタイム クラス オブジェクトに直接アクセスする必要はほとんどありません。 さらに一般的な使用方法は、次の手順に示すように、ランタイム`IsKindOf`クラス オブジェクトを関数に渡す方法です。 この`IsKindOf`関数は、オブジェクトが特定のクラスに属しているかどうかを調べているかどうかをテストします。

#### <a name="to-use-the-iskindof-function"></a>関数を使用するには

1. クラスがランタイム クラスをサポートしていることを確認します。 `CObject`つまり、クラスが直接的または間接的に派生し **、Declare**_**DYNAMIC**および`IMPLEMENT_DYNAMIC`、`DECLARE_DYNCREATE`および`IMPLEMENT_DYNCREATE``DECLARE_SERIAL``IMPLEMENT_SERIAL`マクロを使用して[CObject からクラスを派生する](../mfc/deriving-a-class-from-cobject.md)の記事で説明されている必要があります。

1. 次に`IsKindOf`示すように、そのクラスのオブジェクトのメンバー関数`RUNTIME_CLASS`を呼び出`CRuntimeClass`し、マクロを使用して引数を生成します。

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]

   [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]

    > [!NOTE]
    >  IsKindOf オブジェクトが指定したクラスのメンバーであるか、指定したクラスから派生したクラスのメンバーである場合は**TRUE**を返します。 `IsKindOf`では、多重継承または仮想基底クラスはサポートされませんが、必要に応じて、派生した Microsoft Foundation クラスに対して多重継承を使用できます。

実行時クラス情報の使用の 1 つは、オブジェクトの動的な作成です。 このプロセスについては、「[動的オブジェクトの作成」で](../mfc/dynamic-object-creation.md)説明します。

シリアル化とランタイム クラスの詳細については[、「MFC および](../mfc/files-in-mfc.md)[シリアル化](../mfc/serialization-in-mfc.md)のファイル」を参照してください。

## <a name="see-also"></a>関連項目

[CObject の使い方](../mfc/using-cobject.md)

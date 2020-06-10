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
ms.openlocfilehash: a9f90640007f84c854d59cc27e0c38459c76fe46
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619196"
---
# <a name="accessing-run-time-class-information"></a>ランタイム クラス情報へのアクセス方法

この記事では、実行時にオブジェクトのクラスに関する情報にアクセスする方法について説明します。

> [!NOTE]
> MFC では、Visual C++ 4.0 で導入された[ランタイム型情報](../cpp/run-time-type-information.md)(RTTI) のサポートは使用されません。

[Cobject](reference/cobject-class.md)からクラスを派生させ、 **DECLARE**_**動的**を使用し、「 `IMPLEMENT_DYNAMIC` `DECLARE_DYNCREATE` `IMPLEMENT_DYNCREATE` cobject からクラスを派生させる」で説明されている、および、およびマクロを使用した場合、クラスは実行時 `DECLARE_SERIAL` `IMPLEMENT_SERIAL` [Deriving a Class from CObject](deriving-a-class-from-cobject.md) `CObject` にオブジェクトの正確なクラスを判別できます。

この機能は、関数の引数の追加の型チェックが必要な場合や、オブジェクトのクラスに基づいて特殊な目的のコードを記述する必要がある場合に、最も役立ちます。 ただし、この方法は、仮想関数の機能と重複するため、通常は推奨されません。

メンバー関数は、特定のオブジェクトが特定の `CObject` `IsKindOf` クラスに属しているかどうか、または特定のクラスから派生したものかどうかを判断するために使用できます。 の引数は `IsKindOf` オブジェクトです `CRuntimeClass` 。このオブジェクトは、マクロとクラスの名前を使用して取得でき `RUNTIME_CLASS` ます。

### <a name="to-use-the-runtime_class-macro"></a>RUNTIME_CLASS マクロを使用するには

1. `RUNTIME_CLASS`クラスの名前と共にを使用します。クラスの例を次に示し `CObject` ます。

   [!code-cpp[NVC_MFCCObjectSample#4](codesnippet/cpp/accessing-run-time-class-information_1.cpp)]

実行時クラスオブジェクトに直接アクセスする必要はほとんどありません。 一般的な使用方法は、 `IsKindOf` 次の手順に示すように、ランタイムクラスオブジェクトを関数に渡すことです。 関数は、 `IsKindOf` オブジェクトが特定のクラスに属しているかどうかを調べます。

#### <a name="to-use-the-iskindof-function"></a>IsKindOf 関数を使用するには

1. クラスにランタイムクラスのサポートがあることを確認します。 つまり、クラスは、から直接または間接的に派生 `CObject` し、 **DECLARE**_**DYNAMIC**および、、およびの各マクロを使用して、 `IMPLEMENT_DYNAMIC` `DECLARE_DYNCREATE` `IMPLEMENT_DYNCREATE` `DECLARE_SERIAL` `IMPLEMENT_SERIAL` 「 [CObject からクラスを派生](deriving-a-class-from-cobject.md)させる」で説明されているようにする必要があります。

1. `IsKindOf` `RUNTIME_CLASS` 次に示すように、マクロを使用して引数を生成し、そのクラスのオブジェクトに対してメンバー関数を呼び出し `CRuntimeClass` ます。

   [!code-cpp[NVC_MFCCObjectSample#2](codesnippet/cpp/accessing-run-time-class-information_2.h)]

   [!code-cpp[NVC_MFCCObjectSample#5](codesnippet/cpp/accessing-run-time-class-information_3.cpp)]

    > [!NOTE]
    >  オブジェクトが、指定されたクラスのメンバーであるか、または指定されたクラスから派生したクラスのメンバーである場合、IsKindOf は**TRUE**を返します。 `IsKindOf`は、複数の継承または仮想基底クラスをサポートしていませんが、必要に応じて、派生した Microsoft Foundation クラスに複数の継承を使用できます。

ランタイムクラス情報の使用方法の1つは、オブジェクトの動的な作成です。 このプロセスについては、「[動的オブジェクトの作成](dynamic-object-creation.md)」をご覧ください。

シリアル化およびランタイムクラス情報の詳細については、MFC および[シリアル化](serialization-in-mfc.md)に関する記事の[ファイル](files-in-mfc.md)を参照してください。

## <a name="see-also"></a>関連項目

[CObject の使い方](using-cobject.md)

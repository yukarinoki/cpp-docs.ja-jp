---
description: '詳細情報: MFC クラスオブジェクトの型キャスト'
title: MFC クラス オブジェクトの型キャスト
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
ms.openlocfilehash: bec49afc0050aa32c6e5436e5efca9b0dab30709
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218672"
---
# <a name="type-casting-of-mfc-class-objects"></a>MFC クラス オブジェクトの型キャスト

型キャストマクロは、特定のクラスのオブジェクトを指すポインターに、指定されたポインターをキャストする手段を提供します。キャストが有効であるかどうかをチェックしません。

次の表は、MFC 型をキャストするマクロを示しています。

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>MFC クラスオブジェクトへのポインターをキャストするマクロ

|名前|説明|
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|キャストが有効かどうかを確認しながら、ポインターをクラスオブジェクトへのポインターにキャストします。|
|[STATIC_DOWNCAST](#static_downcast)|オブジェクトへのポインターを1つのクラスから関連する型のポインターにキャストします。 デバッグビルドでは、オブジェクトが対象の型の "種類" ではない場合、はアサートを発生させます。|

## <a name="dynamic_downcast"></a><a name="dynamic_downcast"></a> DYNAMIC_DOWNCAST

キャストが有効かどうかを確認しながら、ポインターをクラスオブジェクトへのポインターにキャストする便利な方法を提供します。

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>パラメーター

*class*<br/>
クラスの名前。

*pointer*<br/>
型 *クラス* のオブジェクトへのポインターにキャストするポインター。

### <a name="remarks"></a>解説

マクロは、 *ポインター* パラメーターを、 *クラス* パラメーターの型のオブジェクトへのポインターにキャストします。

ポインターによって参照されるオブジェクトが識別されたクラスである場合、マクロは適切なポインターを返します。 有効なキャストでない場合、マクロは NULL を返します。

## <a name="static_downcast"></a><a name="static_downcast"></a> STATIC_DOWNCAST

*Pobject* を *class_name* オブジェクトへのポインターにキャストします。

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
キャスト先のクラスの名前。

*pobject*<br/>
*Class_name* オブジェクトへのポインターにキャストするポインター。

### <a name="remarks"></a>解説

*pobject* は、NULL であるか、または *class_name* から直接、または間接的に派生したクラスのオブジェクトを指している必要があります。 _DEBUG プリプロセッサシンボルが定義されたアプリケーションのビルドでは、マクロは、 *pobject* が NULL でない場合、または *class_name* パラメーターで指定されたクラスの "種類" ではないオブジェクトを指している場合にアサートします (「 [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)」を参照)。 **_DEBUG** 以外のビルドでは、マクロは型チェックを行わずにキャストを実行します。

*Class_name* パラメーターで指定するクラスはから派生する必要があり、 `CObject` 「 [cobject クラス: cobject からのクラスの派生](../../mfc/deriving-a-class-from-cobject.md)」で説明されているように、DECLARE_DYNAMIC と IMPLEMENT_DYNAMIC、DECLARE_DYNCREATE と IMPLEMENT_DYNCREATE、または DECLARE_SERIAL マクロと IMPLEMENT_SERIAL マクロを使用する必要があります。

たとえば、 `CMyDoc` `pMyDoc` 次の式を使用するには、ポインターをと呼ばれるポインターにキャストし `CDocument` ます。

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

`pMyDoc`が直接またはから間接的に派生したオブジェクトを指していない場合 `CDocument` 、マクロはをアサートします。

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

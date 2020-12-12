---
description: '詳細については、次を参照してください: CDaoIndexFieldInfo 構造体'
title: CDaoIndexFieldInfo 構造体
ms.date: 09/17/2019
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: fe2d6bef3ce44e7418474b7f2c004942935968c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250791"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo 構造体

構造体には、 `CDaoIndexFieldInfo` データアクセスオブジェクト (DAO) 用に定義されたインデックスフィールドオブジェクトに関する情報が含まれています。

DAO は Office 2013 でサポートされています。 DAO 3.6 は最終バージョンであり、互換性のために残されているものと見なされます。

## <a name="syntax"></a>構文

```
struct CDaoIndexFieldInfo
{
    CString m_strName;          // Primary
    BOOL m_bDescending;         // Primary
};
```

#### <a name="parameters"></a>パラメーター

*m_strName*<br/>
インデックスフィールドオブジェクトに一意の名前を付けます。 詳細については、DAO ヘルプの「Name プロパティ」を参照してください。

*m_bDescending*<br/>
Index オブジェクトによって定義されたインデックスの順序を示します。 順序が降順の場合は TRUE。

## <a name="remarks"></a>解説

インデックスオブジェクトには、複数のフィールドを含めることができます。これは、テーブル (またはテーブルに基づくレコードセット) がインデックス化されているフィールドを示します。 上のプライマリへの参照は、 `m_pFieldInfos` [](../../mfc/reference/cdaoindexinfo-structure.md) `GetIndexInfo` [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)クラスのメンバー関数を呼び出すことによって取得される CDaoIndexInfo オブジェクトのメンバーで情報がどのように返されるかを示します。

インデックスオブジェクトとインデックスフィールドオブジェクトは、MFC クラスでは表されません。 代わりに、 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) クラスまたは [CDAORECORDSET](../../mfc/reference/cdaorecordset-class.md) クラスの MFC オブジェクトの基になる DAO オブジェクトには、Indexes コレクションと呼ばれるインデックスオブジェクトのコレクションが含まれています。 各インデックスオブジェクトには、フィールドオブジェクトのコレクションが含まれています。 これらのクラスは、インデックス情報の個々の項目にアクセスするためのメンバー関数を提供し `CDaoIndexInfo` `GetIndexInfo` ます。また、親オブジェクトのメンバー関数を呼び出すことによって、オブジェクトを使用して一度にすべてのオブジェクトにアクセスすることもできます。 `CDaoIndexInfo`オブジェクトには、 `m_pFieldInfos` オブジェクトの配列を指すデータメンバーがあり `CDaoIndexFieldInfo` ます。

対象 `GetIndexInfo` となるインデックスオブジェクトが格納されているインデックスのコレクションが格納されているテーブルテーブルまたはレコードセットオブジェクトのメンバー関数を呼び出します。 次に、 `m_pFieldInfos` [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) オブジェクトのメンバーにアクセスします。 配列の長さ `m_pFieldInfos` は、に格納され `m_nFields` ます。 `CDaoIndexFieldInfo` は、 `Dump` デバッグビルドでメンバー関数も定義します。 を使用すると、 `Dump` オブジェクトの内容をダンプでき `CDaoIndexFieldInfo` ます。

## <a name="requirements"></a>要件

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef:: GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset:: GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)

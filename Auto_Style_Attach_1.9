// ==UserScript==
// @name        Auto Style Attach ⭐
// @namespace        http://tampermonkey.net/
// @version        1.9
// @description        文書末尾に常設 styleタグを自動記入する
// @author        Ameba Blog User
// @match        https://blog.ameba.jp/ucs/entry/srventryinsertinput.do*
// @match        https://blog.ameba.jp/ucs/entry/srventryupdateinput.do*
// @icon        https://www.google.com/s2/favicons?sz=64&domain=ameblo.jp
// @grant        none
// @updateURL        https://github.com/personwritep/Auto_Style_Attach/raw/main/Auto_Style_Attach.user.js
// @downloadURL        https://github.com/personwritep/Auto_Style_Attach/raw/main/Auto_Style_Attach.user.js
// ==/UserScript==


// 文書保存時（下書きを含む全投稿時）に常設 styleタグを書込みます
// SNSボタン非表示を設定できます（PC表示のみ）


let retry=0;
let interval=setInterval(wait_target, 100);
function wait_target(){
    retry++;
    if(retry>10){ // リトライ制限 10回 1sec
        clearInterval(interval); }
    let target=document.getElementById('cke_1_contents'); // 監視 target
    if(target){
        clearInterval(interval);
        main(); }}


function main(){
    sessionStorage.setItem("jslord_3", "1"); // 📛

    let target=document.getElementById('cke_1_contents'); // 監視 target
    let monitor=new MutationObserver(catch_publish);
    monitor.observe(target, {childList: true}); // 通常・HTML編集切換による発火不能を防ぐ

    catch_publish();

    function catch_publish(){

        panel_add();

        let all_check=document.querySelector('#allFlg');
        if(all_check){
            report();
            all_check.onclick=function(event){
                if(report()==-1){ // HTML表示でチェック不可能
                    event.preventDefault(); }
                else{ // 通常表示でのみチェック可能
                    if(report()==0){
                        insert_ptag(1);
                        report(); }
                    else if(report()==1){
                        insert_ptag(0);
                        report(); }}}}


        function report(){
            let editor_iframe=document.querySelector('.cke_wysiwyg_frame');
            if(editor_iframe){ // iframe読込みが実行条件
                let iframe_doc=editor_iframe.contentWindow.document;
                if(iframe_doc){
                    let iframe_body=iframe_doc.querySelector('body.cke_editable');
                    if(iframe_body){
                        let pts=iframe_body.querySelector('.pts');
                        if(pts){
                            all_check.checked=true;
                            return 1; }
                        else{
                            all_check.checked=false;
                            return 0; }}}}
            else{
                return -1; }}


        function insert_ptag(n){
            let editor_iframe=document.querySelector('.cke_wysiwyg_frame');
            if(editor_iframe){ // iframe読込みが実行条件
                let iframe_doc=editor_iframe.contentWindow.document;
                if(iframe_doc){
                    let iframe_body=iframe_doc.querySelector('body.cke_editable');
                    if(iframe_body){

                        if(n==0){
                            let pts=iframe_body.querySelector('.pts');
                            if(pts){
                                pts.remove(); }}

                        if(n==1){
                            // style_ptext を編集して SNSボタンの非表示内容を変更出来ます ⭕
                            let style_ptext=
                                '<style class="pts" type="text/css">'+
                                '[data-uranus-component="entryAction"], '+
                                '[data-uranus-component="feedbacks"], '+

                                // 以下は 新タイプスキン対応で追加
                                '[data-uranus-component="entryShare"], '+
                                '[data-uranus-component="mainWidget"], '+

                                // 以下は 旧タイプスキン対応で追加（対応不要なら削除可）
                                '.articleExLinkArea, '+
                                '.reblogArea, '+
                                '.commentArea, '+
                                '.pagingArea:nth-of-type(3), '+

                                // 以下は レトロタイプスキン対応で追加（対応不要なら削除可）
                                '#exLinkBtn, '+
                                '#comment_module, '+

                                // 以下は スマホスキン対応
                                '._1oW7Td1- { display: none; }'+
                                '</style>';

                            iframe_body.insertAdjacentHTML('beforeend', style_ptext); } // style.ptsを追加

                    }}}} // insert_ptag(n)


        function panel_add(){
            let l_comm=document.querySelector('.l-communication');
            let p_comm=document.querySelector('.l-communication div:first-child');
            let i_input=p_comm.querySelector('#allFlg');

            if(!i_input){
                let add_comm=p_comm.cloneNode(true);
                let c_title=add_comm.querySelector('h2');
                c_title.textContent='全SNS機能';
                let c_input=add_comm.querySelector('#commentFlg');
                c_input.setAttribute('name', 'allFlg');
                c_input.setAttribute('id', 'allFlg');
                let allFlg_text=add_comm.querySelector('.spui-Checkbox-text');
                allFlg_text.textContent='Close';

                l_comm.insertBefore(add_comm, p_comm); }


            let commFlg_text=l_comm.querySelector('#commentFlg ~ .spui-Checkbox-text');
            commFlg_text.textContent='Close';

            let reblogFlg_text=l_comm.querySelector('#reblogFlg ~ .spui-Checkbox-text');
            reblogFlg_text.textContent='Close';

        } // panel_add()


        // 以下の style_text を編集すると 常設 styleタグ内容を変更出来ます ⭕⭕⭕⭕⭕
        let style_text=
            '<style class="asa" type="text/css">'+
            '@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css"); '+
            '</style>';

        let submitButton=document.querySelectorAll('.js-submitButton');
        submitButton[0].addEventListener('mousedown', insert_tag , false);
        submitButton[1].addEventListener('mousedown', insert_tag , false);

        function insert_tag(e){
            let editor_iframe=document.querySelector('.cke_wysiwyg_frame');
            if(editor_iframe){ // iframe読込みが実行条件
                let iframe_doc=editor_iframe.contentWindow.document;
                if(iframe_doc){
                    let iframe_body=iframe_doc.querySelector('body.cke_editable');

                    if(iframe_body.querySelector('.asa')){
                        iframe_body.querySelector('.asa').remove(); } // 既に書込まれていたら削除して更新する
                    iframe_body.insertAdjacentHTML('beforeend', style_text); }} // 記事末尾に style.asaを追加
            else{
                e.stopImmediatePropagation();
                alert(
                    "　⛔　Auto Style Attach\n"+
                    "　　　常設 styleタグ の書込み・更新のため\n"+
                    "　　　通常表示画面から投稿をしてください"); }}

    } // catch_publish()

} // main()

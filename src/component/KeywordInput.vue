<template>
    <div data-te-modal-init
        class="fixed left-0 top-0 z-[1055] hidden h-full w-full overflow-y-auto overflow-x-hidden outline-none"
        id="keywordInputModal" tabindex="-1" aria-labelledby="exampleModalCenterTitle" aria-modal="true" role="dialog">
        <div data-te-modal-dialog-ref
            class="pointer-events-none relative flex min-h-[calc(100%-1rem)] w-auto translate-y-[-50px] items-center opacity-0 transition-all duration-300 ease-in-out min-[576px]:mx-auto min-[576px]:mt-7 min-[576px]:min-h-[calc(100%-3.5rem)] min-[576px]:max-w-[500px]">
            <div
                class="pointer-events-auto relative flex w-full flex-col rounded-md border-none bg-white bg-clip-padding text-current shadow-lg outline-none dark:bg-neutral-600">
                <div
                    class="flex flex-shrink-0 items-center justify-between rounded-t-md border-b-2 border-neutral-100 border-opacity-100 p-4 dark:border-opacity-50">
                    <!--Modal title-->
                    <h5 class="text-xl font-medium leading-normal text-neutral-800 dark:text-neutral-200"
                        id="exampleModalCenterTitle">
                        請輸入關鍵字
                    </h5>
                    <!--Close button-->
                    <button type="button"
                        class="box-content rounded-none border-none hover:no-underline hover:opacity-75 focus:opacity-100 focus:shadow-none focus:outline-none"
                        data-te-modal-dismiss aria-label="Close">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                            stroke="currentColor" class="h-6 w-6">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
                        </svg>
                    </button>
                </div>

                <!--Modal body-->
                <div class="relative p-4">
                    <div class="relative mb-3" data-te-input-wrapper-init>
                        <input type="text" v-model="keyword"
                            class="peer block min-h-[auto] w-full rounded border-0 bg-transparent px-3 py-[0.32rem] leading-[1.6] outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 peer-focus:text-primary data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200 dark:peer-focus:text-primary [&:not([data-te-input-placeholder-active])]:placeholder:opacity-0"
                            id="exampleFormControlInput1" placeholder="Example label" />
                        <label for="exampleFormControlInput1"
                            class="pointer-events-none absolute left-3 top-0 mb-0 max-w-[90%] origin-[0_0] truncate pt-[0.37rem] leading-[1.6] text-neutral-500 transition-all duration-200 ease-out peer-focus:-translate-y-[0.9rem] peer-focus:scale-[0.8] peer-focus:text-primary peer-data-[te-input-state-active]:-translate-y-[0.9rem] peer-data-[te-input-state-active]:scale-[0.8] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-primary">輸入關鍵字
                        </label>
                    </div>
                    <!-- <div class="relative mb-3" data-te-date-timepicker-init data-te-input-wrapper-init
                        data-te-inline="true">
                        <input 
                        v-model="startDate"
                        type="date"
                            class="peer block min-h-[auto] w-full rounded border-0 bg-transparent px-3 py-[0.32rem] leading-[1.6] outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 peer-focus:text-primary data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200 dark:peer-focus:text-primary [&:not([data-te-input-placeholder-active])]:placeholder:opacity-0"
                            id="form2" />
                    </div>
                     <div class="relative mb-3" data-te-date-timepicker-init data-te-input-wrapper-init
                        data-te-inline="true">
                        <input 
                        v-model="endDate"
                        type="date"
                            class="peer block min-h-[auto] w-full rounded border-0 bg-transparent px-3 py-[0.32rem] leading-[1.6] outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 peer-focus:text-primary data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200 dark:peer-focus:text-primary [&:not([data-te-input-placeholder-active])]:placeholder:opacity-0"
                            id="form2" />
                    </div> -->
                </div>

                <!--Modal footer-->
                <div
                    class="flex flex-shrink-0 flex-wrap items-center justify-end rounded-b-md border-t-2 border-neutral-100 border-opacity-100 p-4 dark:border-opacity-50">
                    <button type="button"
                        class="inline-block rounded bg-primary-100 px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-primary-700 transition duration-150 ease-in-out hover:bg-primary-accent-100 focus:bg-primary-accent-100 focus:outline-none focus:ring-0 active:bg-primary-accent-200"
                        data-te-modal-dismiss data-te-ripple-init data-te-ripple-color="light">
                        關閉
                    </button>
                    <button type="button"
                        class="ml-1 inline-block rounded bg-primary px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#3b71ca] transition duration-150 ease-in-out hover:bg-primary-600 hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:bg-primary-600 focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:outline-none focus:ring-0 active:bg-primary-700 active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(59,113,202,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)]"
                        data-te-modal-dismiss @click="search">
                        確認
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>
<script setup lang="ts">
import { getHashTag, getUserInfo } from '@/api'
import useUtils from '@/composables/useUtils'
import { useLoadingStore } from '@/store/useLoadingStore';
import { useUserStore } from '@/store/useUserStore';

const { formatDate } = useUtils()
const { setLoading, setLoadingText, resetLoadingText } = useLoadingStore()
const { pushUserList, resetUserList } = useUserStore()



const keyword = ref('')
const startDate = ref(new Date())
const endDate = ref(new Date())

let requestCount = 0
let maxRequest = 10
let hasNextPage = false
async function search() {
    if (!keyword.value) return alert('請輸入關鍵字')
    //開啟Loading畫面
    setLoading(true)
    //各種初始化的重置
    resetUserList()
    //請求使用者的shortcode，並獲取userList
    fetchUserShortCodeAndGetUserName()
    // console.log(startDate.value)
    // console.log(endDate.value)
}
async function fetchUserShortCodeAndGetUserName(cursor?: string): Promise<any> {  //會去爬shortCode
    if (requestCount >= maxRequest) { //最後一次請求，關閉loading
        resetFetchData();
        return
    }
    else if (requestCount === maxRequest) setLoadingText('求取最後一批資料!')
    else setLoadingText('請求資料...')

    try {
        requestCount++  //每執行一次就算一次
        console.log('執行了第幾次', requestCount)
        const users = await getHashTag({
            keyword: keyword.value,
            start: formatDate(new Date('2023-12-22 17:00:00')),
            end: formatDate(new Date('2023-12-22 21:00:00')),
            cursor
        })

        if (users?.status !== 200) return
        if (users.data.edges.length === 0) return resetFetchData()
        //若有下一頁，則繼續call下一頁
        if (users.data.has_next_page) {
            console.log('有下一頁', '當前頁', requestCount)
            fetchUserShortCodeAndGetUserName(users.data.cursor)
            hasNextPage = true
        } else {
            console.log('沒有下一頁')
            hasNextPage = false
        }

        //若有搜尋結果處理
        if (requestCount === maxRequest) setLoadingText('最後一次比對...就快好啦~~~~~~')
        else setLoadingText('進行資料比對...請耐心等候')

        const datas = users?.data.edges.map((user: any) => user.node.shortcode)
        const shortcodes = []
        shortcodes.push(...datas)
        //用short請求使用者的資訊
        const promiseArray: Promise<any>[] = []

        shortcodes.forEach(shortcode => {  //一一非同步的去請求
            promiseArray.push(getUserInfo({ shortcode }))
        })
        const result = await Promise.allSettled(promiseArray)
        result.forEach((res: any) => {
            if (res.status === 'fulfilled') {
                pushUserList({
                    id: new Date().toDateString(),
                    name: res?.value.data.owner.username
                })
            }
        })
        if (!hasNextPage) {
            console.log('沒下一頁了，關閉')
            return resetFetchData()
        }
    } catch (err) {
        console.log('第', requestCount, '次請求，超時，自動繼續執行')
        if (requestCount === 1) return fetchUserShortCodeAndGetUserName()
        fetchUserShortCodeAndGetUserName(cursor)  //請求時如果失敗，自動再請求一次~
    }
}

function resetFetchData() {
    setLoading(false);
    resetLoadingText();
    console.log('結束返回', requestCount);
    requestCount = 0;
}
</script>
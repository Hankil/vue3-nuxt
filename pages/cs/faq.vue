<template>
  <div>
    <div>
      <h2 class="text-2xl font-medium">자주하는 질문</h2>
      <p>FAQ 페이지를 통해 궁금증을 해결하세요.</p>
    </div>
    <div class="flex">
      <Select>
        <SelectTrigger>
          <SelectValue placeholder="카테고리" />
        </SelectTrigger>
        <SelectContent>
          <SelectGroup>
            <!-- <SelectLabel>Fruits</SelectLabel> -->
            <SelectItem value="all"> 전체 </SelectItem>
            <SelectItem value="opt1"> OPT1 </SelectItem>
            <SelectItem value="opt2"> OPT2 </SelectItem>
          </SelectGroup>
        </SelectContent>
      </Select>
      <Input />
      <Button>검색</Button>
    </div>

    <div class="mt-10">
      <div class="flex">
        <Select>
          <SelectTrigger>
            <SelectValue placeholder="선택" />
          </SelectTrigger>
          <SelectContent>
            <SelectGroup>
              <SelectItem value="10"> 10개 </SelectItem>
              <SelectItem value="20"> 20개 </SelectItem>
            </SelectGroup>
          </SelectContent>
        </Select>
        <div>
          <p>전체 <span class="font-medium color-primary">12</span>개</p>
          <p>총 12건이 검색되었습니다.</p>
        </div>
      </div>
      <div>아코디언테이블</div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped></style>

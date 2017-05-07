# muslx32toolkit
BASH Scripts for Gentoo Linux to build stage3 and stage4 images using crossdev for the muslx32 platform


Step 1: chmod +x prepare

Step 2: Run ./prepare

Step 3: Move the muslx32toolkit folder into the same folder as the stage3 and portage snapshot

Step 4: Run ./build-crossdev-toolchain

(chroot)

Step 5: Run ./create-stage3

(chroot)

Step 6: Run ./create-stage4

(chroot)

Step 7: Run ./fixstage4 corrective script if in the step 6's create-stage4 script fails then repeat step 7
